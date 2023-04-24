# Python Built-in Data Types
Last week, we looked at lists, strings, numbers, and dictionaries. Today, we'll learn more about Python's built-in data types and get some more practice with Python foundations.

# Python Data Types, Lists, and Dictionaries

Alright, now back to Python! We'll continue with the basics, looking at some built-in data types. We'll focus especially on lists and dictionaries.

<br>

## Built-in data types

Python has a number of [built-in data types](https://docs.python.org/3/library/stdtypes.html) to allow us to work with many different kinds of data. 

We are typically most interested in the **numeric** types (int, float), **text** (str), **collections** (list, tuple, range), and **boolean** types. 

For your reference, here is the complete list of built-in types:
- Text Type: str
- Numeric Types: 	int, float, complex
- Collection Types: list, tuple, set, dict
- Set Types: 	set, frozenset
- Boolean Type: 	bool
- Binary Types: 	bytes, bytearray, memoryview

'Boolean' types can only have two values, "True" or "False". 

All primitive types include members (or methods) that perform various actions. For example the `str` type has methods to capitalizing (upper case), lower case, search for phrases within the string, or replace phrases. Let's take a look at some of the `str` members.

You can access primitive type methods by including a `.` after the variable name and then adding the member name. For example:

```python
name = "data stack"
name.upper()
```

This will uppercase our name variable. Members are functions. You'll learn more about functions later; to invoke a function you need to include `()` at the end of its name (ie: `.upper()`). If the function takes any arguments (parameters), they are included in between the opening `(` and closing `)` parenthesis. 

You can always use the _Code Completion_ feature of VS Code to see a list of available members for a data type. Enter your variable name and a trailing dot `.` to start invoking its members, then press `CTRL` + `SPACE` to open the code completion window. You can scroll through the list of available members and choose the one you like to invoke.

<br>

### Numeric Types
Before we continue with more complex data types like strings and collections, let's take a quick look at numeric types.

The two main numeric types are int (whole numbers) and float (decimal numbers).

```python
# int assignment (whole numbers)
x = 3

# float assignment (numbers with decimals)
pi = 3.14159265359

# print values
print(x, pi)
```

For details and practice with strings, lists, and dictionaries, work through notebooks `01_strings.ipynb`, `02_lists.ipynb`, and `03_dictionaries.ipynb`.

Once you're done with the notebooks, head to the `exercises` folder for more practice.
<br>
## Goals for Today
