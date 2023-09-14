# Command Line

_"Graphical user interfaces make easy tasks easy, while command line interfaces make difficult tasks possible._     -William Shotts, 'The Linux Command Line'


Before we dive back into Python, let's learn some command-line interface (CLI) tools. The command-line lets your search and navigate your file system, change the kinds of permissions on files, configure your environment, and much more. We've already used it for Git and GitHub. Here, we'll learn other common commands. 

The commands described here are standard on any Linux-flavored OS, but they might not all be available on every system, depending on your distribution. Because Mac OS is based on Free BSD, most (though not all) standard Linux commands are available from a Mac OS terminal.

You can find out more about these commands by looking up their man (manual) pages with `man <command_name>` . You're also encouraged to Google commands for more info. For example, here's a [link](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/?ref=lbp) for working with the `find` command.


Test each of the commands below, and observe the output. If a command is stalling out, you can stop it by typing `Ctrl + c`.

> Nothing in this lesson is dangerous, but use the commands to move or remove files with caution. When you get more advanced, be cautious about terminal commands you find on the internet; some of them can delete a lot of information.

 ## Navigation
We've already learned how to use `cd` to change directories.

You can traverse the file tree in two ways:
- Absolute path, which starts at the root and lists every directory til the destination, or
- Relative path, which starts from the directory you're currently in.

To get the absolute path to the directory you're in ("present working directory"), use `pwd`.

Here's an example of using an absolute path (silly here, but there are cases where it's useful):

![absolute path example](./imgs/absolute_path.png)

...and an example using relative path:

![relative path example](./imgs/relative_path.png)

Sometimes in a code file you'll see a path written with `./` at the beginning. That means, "start in the directory containing this file. If you look at the raw Markdown for the README.md file we're in right now, you'll see paths like `./imgs/relative_path.png`, meaning, "start in the `ep3` directory containing this `README`, then go to the `imgs` folder that's also there. Check out the folder for this episode in VSCode or GitHub to see what it contains.

`cd` has a few useful shortcuts:

`cd -` changes the directory to the previous working directory. Note that this is previous like "most recent", not like "the one above it in the file tree". For illustrations:

![cd with hyphon shortcut](./imgs/cd_hyphen.png)

`cd ~` takes you back to the home directory.


## Contents of a Directory
You've also already used `ls` to list the contents of the directory your currently in. It has many additional options, but we'll just look at two.
    
`ls -l` lists your files in 'long format', which contains lots of information that will be useful as you advance. For example:

![list long](./imgs/list_long.png)

Let's break it down:

|Field | Meaning |
|----|----|
|drwxrwxr-x|The first character is the type of file: 'd' is a directory, '-' is a file. The rest are permissions: 'r' for 'read', 'w' for 'write', 'x' for 'execute'. The first three are for the file's owner, the middle three are for members of the file's group, and the last three are for everyone else. Permissions are an advanced topic that we'll visit in bootcamp.|
|4|Number of hard links to the file, including itself and its parent directory|
|alma|The file's owner|
|alma|The group that owns the file|
|4096|The size of the file, in bytes|
|Sep 13 17:34|When the file was last modified|
|ep1|The file's name|




`ls -a` lists all files. itemnames that begin with a `.` are normally hidden, usually because they should only be modified with caution. 

> Note: itemnames in Linux are case sensitive. Use an underscore or hyphen to separate words, instead of whitespace, which will cause the words to be read as separate names in the terminal. 

`less <itemname>` shows the contents of a file. Use the arrow keys to scroll, or `q`` to quit. 

## Making, Moving, and Removing Files and Directories
`mkdir <dirname>` makes a new directory in the directory you're currently in. You can use `mkdir` followed by several folder names, and they'll all be created at once.

`mv <itemname1> <itemname2>` moves `<itemname1>` into `<itemname2>`, if `<itemname2>` exists. Otherwise, `<itemname1>` gets renamed as `<itemname2>`. You can't move the directory you're currently in.

`touch <itemname>` creates a file in the directory you're currently in.

`rm <itemname>` deletes the item. Careful! You won't get a warning, and it can't be reversed. `rm` has some useful options:

|Short name|Long name|Purpose|
|----|----|----|
|-i|--interactive|Prompt the user for confirmation before deleting|
|-r|--recursive|This has to be used if you're deleting a directory that contains subdirectories|
|-v|--verbose|Show info about the deletion|

You can use several options at once, like this: `rm -rv <dirname>`



### Exercise
- In your terminal, navigate to the week_2/ep3 folder
- Use `mkdir` to create two new directories, `thing1` and `thing2`
- In `thing2`, use `touch` to create a file
- Use `mv` to move `thing2` into `thing1`
- `ls` the contents of `thing1` to make sure that worked
- Recursively remove `thing1` and its contents

- Hint: for each step, make sure you're in the right directory.

## Writing to a File

`echo "hello"` - print a message to the console

`echo "hello" > <filename>` - use the redirect symbol (`>`) to direct the output of `echo` command into a file

`cat <filename>` - display the content of <filename>

`echo " world" >> <filename>` - use the redirect-append symbol (`>>`) to append the output of `echo` command into an existing file

`cat test.txt` - display the content of test.txt

    

    
`nano <itemname>` - Nano is an editor that lets you create and edit a file. See the [beginner's guide to nano](https://itsfoss.com/nano-editor-guide/).
    
`mv <itemname1> <itemname2>` - moves a file (i.e. gives it a different name, or moves it into a different directory (see below)
    
`cp <itemname1> <itemname2>` - copies a file
    
`rm <itemname>` - removes a file. It is wise to use the option rm -i, which will ask you for confirmation before actually deleting anything. You can make this your default by making an alias in your .cshrc file.
    
`diff <itemname1> <itemname2>` - compares files, and shows where they differ
    
`wc <itemname>` - tells you how many lines, words, and characters there are in a file
    
`chmod [options] <itemname>` - lets you change the read, write, and execute permissions on your files. The default is that only you can look at them and change them, but you may sometimes want to change these permissions. For example, chmod o+r itemname will make the file readable for everyone, and chmod o-r itemname will make it unreadable for others again. Note that for someone to be able to actually look at the file the directories it is in need to be at least executable. See [this guide to Linux permissions](https://opensource.com/article/19/6/understanding-linux-permissions) for more details.

<br/>

## Directories
Directories are used to group files together in a hierarchical structure. It's basically a folder. Here are some commands for navigating directory structure.

`mkdir <dirname>` - make a new directory

`cd <dirname>`  - change directory. Your working directory (where you are) will change, and you will see the files in that directory when you do `ls`. You always start out in your home directory, and you can get back there by typing `cd` without arguments. `cd ..` will get you one level up from your current position. `cd ../..` will get you two levels up from your current position, and so on. You don't have to walk along step by step - you can make big leaps or avoid walking around by specifying pathnames.
    


<br/>


## About your (electronic) self
`whoami` - returns your username. Sounds useless, but isn't. You may need to find out who it is who forgot to log out somewhere, and make sure *you* have logged out.

`ps` - lists running processes. Contains lots of information about them, including the process ID, which you need if you have to kill a process. 

`ps aux | grep chrome` - list processes and filter to only running chrome processes

`kill <PID>` --- kills (ends) the processes with the ID you gave. Get the ID by using `ps``. If the process doesn't 'die' properly, use the option -9. But attempt without that option first, because it doesn't give the process a chance to finish possibly important business before dying. 
    
`pkill <PNAME>` - kill a particular process using the process name

`du <itemname>` - shows the disk usage of the files and directories in itemname (without argument the current directory is used). du -s gives only a total.
    
`df` - shows a list of disks on the system and the amount of disk space used

<br/>



## Goals for Today
- Learn more about using the command line
