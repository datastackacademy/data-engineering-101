# Welcome
Welcome to class! This first day will be a gentle intro to the Python programming language and the Linux command line. We've built in time for asking questions and getting oriented.

## Python
Code is a set of instructions, and there are a lot of languages you can use to write it. So, why Python?

Python is:
- Widely used in data engineering.
- Supported by a large online community.
- Easy to read and debug.
- Actually pretty fun, once you get the hang of it.


## Google Colab
In bootcamp, and in the rest of this course, we'll write Python in an application called VS Code. For today we'll use Google Colab.

Colab lets you:
- Include blocks of text, called 'Markdown', throughout your code.
- Write code in cells, so you can run a single cell or a whole program.
- Start using Python without setting up a local environment.

The Python tutorial we use today is adapted from the [Data Stack Academy 5 Day Python Challenge](https://drive.google.com/drive/folders/1FxlXQNr1bgL67o5PcxNDTkRHqhiOLPRR?usp=share_link). In order to interact with the notebooks, you'll need a Google account.

Log into a Google account, then [click here to open notebook 1](https://colab.research.google.com/drive/1d-kGaUWYM7SfM38LOOBXvV6ETQH0BQ2n?usp=sharing), where you can find lessons on the basics of Python and notebooks. Then you can keep going in [notebook 2](https://colab.research.google.com/drive/1JyqPk1WabYuac9Himwo4bnF_e8ms4-fS?usp=sharing) to learn the more advanced concept of the dictionary data structure.

Make sure you save time before the end of class to get to the lesson about the terminal below.


## The Terminal
Tomorrow's instructions have you using your terminal. The terminal is how you interact with your operating system. You can open it by clicking on the terminal icon on your desktop. If you don't see one, search for how to open a terminal on whatever operating system you're using.

The commands below are in Linux, the operating system we teach in bootcamp, but they'll also work on Mac OS. Windows users can follow the notes. Tomorrow, Windows and Mac users will learn how to use Linux terminals on their operating systems. 

When you first open a terminal, it looks something like this:

![new terminal](./imgs/fresh_terminal.png)

...your username `@` your computer name, then `$`. This is your root directory. 

The file system is hierarchical, starting at the root and branching off. Think of it like an upside-down tree: a folder can contain folders that each contain folders, etc. In this lesson, we'll see how to navigate a path from the root to the leaves and back.

To see what's in a directory, use the command `ls` (for 'list').

> Windows: use `dir` instead of `ls`

![ls example](./imgs/ls.png)

You can see the files in one color, and the directories in another. To move down a directory, use `cd` (for 'change directory') followed by the directory name. This example has a 'repos' directory, so let's move there and list what's in it:

![cd and ls example](./imgs/cd_and_ls.png)

You can use `cd` to move several directories down at once. It'll be different on your machine, but in this example the directory `DE101_Sept_2023` contains the repository for this bootcamp curriculum, matching what you're looking at here on GitHub. To move to week 1, episode 1 of the curriculum, we'd do `cd DE101_Sept_2023/week_1/ep1`:

![cd several dirs at once](./imgs/cd_several_directories.png)

> Windows: separate directories with a `\` instead of `/`

To move back up a directory, use `cd ..`:

![cd up a dir](./imgs/cd_up_a_dir.png)

We'll be working with the terminal often, so play with this til your comfortable. `cd` (or `dir` for Windows) and `ls` won't break anything. 

It can help to look at your file system on your desktop, and compare it to navigating in the terminal.


## Goals for Today
- Start learning the very basics of Python
- Get familiar with Colab
- Start navigating in the terminal



