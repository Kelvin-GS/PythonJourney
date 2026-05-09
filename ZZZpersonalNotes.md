#### Built in Python functions

The Python Standard Library has some built in functions. Some of these useful functions are:

| Function              | Meaning                                               |
| :-------------------- | :---------------------------------------------------- |
| `len(x)`            | **length** of x                                 |
| `pow(x, n)`         | x to the**power** n (x**n)                      |
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

#### MODULES

print(math.pi)   # 𝜋 (3.3.1415...)
print(math.e)    # Euler constant (2.7182...)

#### STRING CONCATENATION

We observe that:

* the `print()` adds one space in between strings. This can be changed with the `sep` argument of the `print()` function.
* At the end of the line, `print()` adds a newline character. This can be changed with the `end` argument of the `print()` function.
* with the `+` operator strings are concatenated without extra spaces in between
* string duplication with the `*` operator saves typing time

  ```
  print(word1, word2, word3, sep = "***", end = ";)-")    # Instead of white space, adds what ever is in "sep"
  ```

#### String manipulation

Often we need to manipulate strings:

* search for a character or a substring,
* count the numberof occurances,
* replace one or more characters by others,
* split the string,
* etc.

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

* `start` is the index of the first element (default is 0),
* `stop` is the index of the last element (**not included**, default is len(list_name)) and
* `step` is the number of elements to skip (default is 1).

**Example:**

`print(s[0:4])   # select characters with indices 0 up to 3`

|    Slice    | Meaning                                                                       |
| :----------: | ----------------------------------------------------------------------------- |
|   `s[i]`   | character at index `i` (counting starts at 0)                               |
|  `s[i:j]`  | characters `i` up to `j-1` (character `j` **not** included)       |
|  `s[i:]`  | characters from `i` up to end of string                                     |
|  `s[:j]`  | characters from start up to `j-1` (character  `j` **not** included) |
| `s[i:j:k]` | characters from `i` up to `j-1` in steps of `k`                         |
|   `s[:]`   | all characters                                                                |
| `s[::-1]` | all characters in**reversed** order                                     |

#### Basic formatting

To use `f` strings:

* place an `f` or an `F` before the string to be formatted
* type accolades `{}` (_place holders_) around the variable to be formatted
* let the variable be followed by a colon `:`
* specify the datatype of the variable:

| Character | Datatype |
| :-------: | -------- |
|   `s`   | string   |
|   `d`   | integer  |
|   `f`   | float    |

* print the `f` string with the `print()` function

The syntax to format a variable is

```Python
    {variable:xtype}
```

with:

* `variable`: the name of the variable to be formatted
* `x`: the number of characters (places) to be used
* `type`: the datatype of the variable to be formatted (`s`, `d` or `f`)

```
char = "a"
n = 23
print(f"The character {char:5s} occurs {n:10d} times")  # THis leaves 5 spaces for the variable "char" and 10 spaces for "n"

# Output is : The character a     occurs         23 times
```

```
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
