# Python Built-in Data Types
Today, we'll review and practice the lists, strings, numbers, and dictionaries. We'll also learn about flow control, which is how we tell the code what order to run in.

## Built-in data types

Python's [built-in data types](https://docs.python.org/3/library/stdtypes.html) are the building blocks of the language. We've already learned about the numeric types (int, float), text (str), and a few collections (list, dict). 

These are the types you'll use most often, along with Booleans. 'Boolean' types are easy: they can only have two values, "True" or "False". 

For your reference, here is the complete list of built-in types:
- Text Type: str
- Numeric Types: 	int, float, complex
- Collection Types: list, tuple, set, dict
- Set Types: 	set, frozenset
- Boolean Type: 	bool
- Binary Types: 	bytes, bytearray, memoryview


All primitive types include members (or methods) that perform various actions. For example the `str` type has methods to capitalizing (upper case), lower case, search for phrases within the string, or replace phrases. Let's take a look at some of the `str` members.

You can access primitive type methods by including a `.` after the variable name and then adding the member name. For example:

```python
name = "data stack"
name.upper()
```

This will uppercase our name variable. Members are functions. You'll learn more about functions later; to invoke a function you need to include `()` at the end of its name (ie: `.upper()`). If the function takes any arguments (parameters), they are included in between the opening `(` and closing `)` parenthesis. 

You can always use the _Code Completion_ feature of VS Code to see a list of available members for a data type. Enter your variable name and a trailing dot `.` to start invoking its members, then press `CTRL` + `SPACE` to open the code completion window. You can scroll through the list of available members and choose the one you like to invoke.

## Review and Practice
In the `notebooks` folder of this episode, you'll find `01_strings.ipynb`, `02_lists.ipynb`, and `03_dictionaries.ipynb`. In order to run notebooks, you'll need to have Jupyter installed in the virtual environment for week_2/ep1. 
.
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
There are two Python collection data types: tuples and sets. 

Tuples are an ordered, unchangeable collection that allows duplicate members. They're a lot like lists; the main difference is that lists can be changed with methods like `pop()` and `append()`, while tuples cannot. 

Sets are an unordered and unindexed collections that do not allow duplicates. They are less commonly used than lists or dicts but still serve an important role.

Head to notebook '04_sets_and_tuples.ipynb' for more instruction and practice.

## Collection summary
Now you know all the basic types of Collections you will encounter in Python. These will serve as the building blocks for your future work in data engineering with Python. Let's give a quick summary of them so you know what collection to use when a project requires you to store multiple objects:
- `list` - The simplicity and flexibility of `lists` means you will often use them whenever you simply need to store multiple values. As ordered collections, they are great for storing items sequentially, which also makes them great for iteration. They are not well suited to finding specific items inside them since there is no labeling on the values.
- `dict` - These are great any time you want to store labeled values for future use, which happens often. They are often used to store configuration information because of this feature. They are also great for iterating over and allow you to check the label before performing certain actions as well. Additionally as of Python 3.7, the items can be iterated over in the order they were added, similar to a list.
- `tuple` - an ordered, unchangeable set of values. Tuples will show up most often in return values from functions. Their more rigid structure is well suited to functions interacting with each other; if you expect a specific number of returned values, a `tuple` won't let you down.
- `set` - probably the least frequently used collection type but they have utility when you want to keep unique values and/or check if an input is in a specific set of values. You won't use them often, but every once in a while, they'll be exactly what is needed.

## Exercises
Once you're done with the notebooks, head to the `exercises` folder for more practice.

## Goals for Today
- Better understand the elements of Python
- Practice using strings, dictionaries, and lists