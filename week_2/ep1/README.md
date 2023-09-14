# Python Built-in Data Types
Today, we'll review and practice lists, strings, numbers, and dictionaries. We'll also learn about flow control, which is how we tell the code what order to run in.

## Built-in data types

Python's [built-in data types](https://docs.python.org/3/library/stdtypes.html) are the building blocks of the language. We've already learned about the numeric types (int, float), text (str), and a few collections (list, dict). 

These are the types you'll use most often, along with Booleans. Boolean types are easy; they can only have two values, "True" or "False". 

For your reference, here is the complete list of built-in types:
- Text Type: str
- Numeric Types: 	int, float, complex
- Collection Types: list, tuple, set, dict
- Set Types: 	set, frozenset
- Boolean Type: 	bool
- Binary Types: 	bytes, bytearray, memoryview


All primitive types include methods that perform various actions. For example the `str` type has methods to change a string to upper case or lower case, to search for phrases within the string, to replace phrases, and many more. We'll take a look at some of the `str` methods.

You can access methods by including a `.` after the variable name, then adding the method name followed by parenthesis. For example:

```python
# make a variable that holds a string
school = "data stack"

# use a method
school.upper()
```

This will uppercase our name variable. Methods are functions. You'll learn more about functions later, but for now just know that functions do an action. To make a function run you need to include `()` at the end of its name (ie: `.upper()`).

You can always use the code completion feature of VS Code to see a list of available methods for a data type. Enter your variable name and a trailing dot `.` to see a list of its methods, then press `CTRL` + `SPACE` to open the code completion window. You can scroll through the list of available methods and choose the one you like to invoke.

## Review and Practice
In the `notebooks` folder of this episode, you'll find `01_strings.ipynb`, `02_lists.ipynb`, and `03_dictionaries.ipynb`. In order to run notebooks, you'll need to have Jupyter installed in the virtual environment for week_2/ep1. 

Remember from last week to:

- Create a Python virtual environment
```
python3.7 -m venv venv
```

- Activate it
```
source venv/bin/activate
```

- Install the requirements (make sure you're in week_2/ep1)
```
pip install -r requirements.txt
```

## Tuples and Sets
In addition to lists and dictionaries, there are two more Python collection data types: tuples and sets. 

Tuples are an ordered, unchangeable collection that allows duplicate members. They're a lot like lists; the main difference is that lists can be changed with methods like `.pop()` and `.append()`, while tuples cannot. 

Sets are an unordered and unindexed collections that do not allow duplicates. They are less commonly used than lists or dicts but still serve an important role.

Head to notebook `04_sets_and_tuples.ipynb` for more instruction and practice.

## Collection summary
Now you know all the basic types of collections you will encounter in Python. These will serve as the building blocks for your future work in data engineering with Python. Let's give a quick summary of them so you know what collection to use when a project requires you to store multiple objects:
- `list` - The simplicity and flexibility of `lists` means you will often use them whenever you simply need to store multiple values. As ordered collections, they are great for storing items sequentially, which also makes them great for iteration. They are not well suited to finding specific items inside them since there is no labeling on the values.
- `dict` - These are great any time you want to store labeled values for future use, which happens often. They are often used to store configuration information because of this feature. They are also great for iterating over and allow you to check the label before performing certain actions as well. Additionally as of Python 3.7, the items can be iterated over in the order they were added, similar to a list.
- `tuple` - an ordered, unchangeable set of values. Tuples will show up most often in return values from functions. Their more rigid structure is well suited to functions interacting with each other. If you expect a specific number of returned values, a `tuple` won't let you down.
- `set` - probably the least frequently used collection type, but they have utility when you want to keep unique values and/or check if an input is in a specific set of values. You won't use them often, but every once in a while, they'll be exactly what is needed.

## Flow Controls
In Python, 'flow control' means how the code is executed, based on a condition. Today, we're going to look at `for` loops, `while` loops, and `if` conditions. Please work through notebooks `05_for_loops.ipynb`, `06_while_loops.ipynb`, and `07_if_conditions.ipynb` before moving on.

Once you're familiar with `for` loops, `while` loops, and `if` conditions, go to notebook `08_flow_control_misc.ipynb` for more info about how flow controls can be used.

## Exercises
When you're done with the notebooks, head to the `exercises` folder for more practice.

## Goals for Today
- Better understand the elements of Python
- Practice using strings, dictionaries, lists, and flow controls
