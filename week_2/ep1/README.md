# Python Built-in Data Types
Last week, we looked at lists, strings, numbers, and dictionaries. These are the foundations of Python, so we'll review and practice them today. We'll also learn more about Python's built-in data types.

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

Once you're done with the notebooks, head to the `exercises` folder for more practice.

## Goals for Today
- Better understand the elements of Python
- Practice using strings, dictionaries, and lists