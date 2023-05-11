# Git, GitHub, and Project Setup

In the first part of today's lesson, we'll be practicing Git and GitHub. These are essential tools for version control, collaboration, and presenting your work. In bootcamp, you'll use Git and GitHub for your weekly code reviews and your team projects. You'll also probably use them in the rest of your data engineering career.

Git is an open source software used for version control. [GitHub](https://github.com/) is the industry standard for using Git to collaborate on development projects, and to store a portfolio of your own projects (projects on GitHub are called repositories, or repos). 

We'll also go over general setup for the kinds of projects you'll have on GitHub. 

## Make a Profile
If you don't already have a GitHub profile, make one now! Go to [https://github.com/](https://github.com/) and click 'Sign Up', then follow the prompts. 

There are lots of ways to customize your settings, but a basic profile is fine for now.

Take some time to click around on your new GitHub profile to explore the tabs.


## Key Terms

### Remote Repositories and Local Repositories
You can think of a local repo as the version of a project you have on your own computer, where you can make changes to share later, and a remote repository as the one on GitHub, seen by everyone. 

### Initializing a Repository
This makes a unversioned project into a Git repository by creating a .git subdirectory. Run this command one time when you're setting up your project:
```
git init
```
If you try to run a git command, like `git status`, and get the error message `fatal: not a git repository (or any of the parent directories): .git`, it's probably because you didn't `git init`.

### Forking and Cloning
In the [course-overview section](https://github.com/datastackacademy/data-engineering-bootcamp/blob/main/getting-started/course-overview.md) you saw how to fork the remote Data Engineering Bootcamp repo, so you had your own remote copy of it.
You can also create a local repo from a remote by cloning it. A forked repository is a completely independent copy, while a cloned one is sychronized with the remote.

### Pushing and Pulling
Push changes from local -> remote. Pull changes remote -> local.

> "Remote" means GitHub. "Local" means your personal computer.

### Commit Messages
'Committing' will create a record of your changes in the project's version history. When you commit changes, include a short message of what you did and why. These messages show up in the version history too. Writing useful messages can save you a lot of trouble if you need to troubleshoot later.

By convention, commit messages are written in the present tense, like this:
```bash
git commit -m "do a thing"
```

### Branches, Pull Requests, and Merging
On both the remote and local, the `main` branch is the official version of the project. Creating a branch makes a copy of the project where you can play around and make changes without affecting the `main` branch. 

If you like the changes you made on your local branch, you can push them to a corresponding remote branch and create a pull request. A pull request is a way of asking your collaborators to merge your changes with the remote `main` branch, making them part of the shared, official version of the project.

## Git Flow Basics

Git and GitHub can become quite complex, especially when you're collaborating with others. Today, we'll just practice basic solo projects, like the repositories you'll submit for code reviews in this course.

#### Without Branches
This is the simplest way to use Git. The flow is:
- Make changes to your files in VS Code.
- Save the changes in VS Code.
- In your terminal, use the command `git add <file_name>` to add each changed file to Git's staging area. If the file isn't in your terminal's present working directory, you'll also have to include the relative path. Do NOT add files with `git add *`, which can accidentally include files that ought to be excluded.
> The command `git status` will show you what files have been changed since the last commit.
- `git commit -m "<commit_message>"` will commit the changes to the project's history. What was changed, when it was committed, and the commit message all become part of the project's record. You can look at the commit history using Git or GitHub.

Committing often makes it easier to find and fix errors.

- `git push <remote_name> <remote_brach>` sends the committed changes from your local (VS Code) to the remote (GitHub). Nobody else can see the changes until you push them. 
Usually, the remote name will be "origin". If there aren't any branches, the main branch defaults to 'main', so the command is `git push origin main`. But this breaks one of the golden rules of Git: don't push to `main`! In a collaborative or production setting, the `main` branch the official version of the project that has been reviewed and agreed on. Pushing to a branch instead allows you and your peers to review changes before they become the official version of the project.

#### With Branches
Even when you're working alone, get in the habit of using branches. The flow is:
- If you're on the main branch, the command `git checkout -b <branch_name>` will create a new branch off main and switch to it. "Create a new branch off main" means that you start with a version of the project that's exactly like the one you branched off. 

Give your branch a name that describes the way that branch is different from `main`, like "random_numbers" or "refactored". You can switch between existing branches with `git checkout <branch_name>`.

- Make, add, and commit changes on your branch.
- Push the changes from a local branch to a remote branch. Using `git push <remote_name> <branch_name>` will create a branch on GitHub with the same name as the local branch you're on, if one doesn't already exist.
- When you want to add the changes on your branch to the main version of the project, open a pull request. We'll look at this in more detail below. When you're working with others, a pull request lets your peers look at the changes and make suggestions before pulling them into `main`.


## Project Setup
Every week, you'll use GitHub to share a repository for your code review project. Nearly all of these will include:
- A `requirements.txt` file: it's just a list of the packages that the project in the repository needs to install before it can run. If you include a `requirements.txt` file your user can just run
`pip install -r requirements.txt`
in the terminal with the virtual environment activated, then start running the code in the repo.
- A `README.md` file: you're in one now! It's the main documentation for a project, and it's what shows up on the main page of a GitHub repo. In the Data Stack Academy repository, we use the README to orient you to the content of the each episode. For your code review projects, you'll usually want to include a description of the project, a list of the technologies used, a list of the known bugs, and a diagram of how the pieces in your project fit together.
- A `.gitignore` file: there will often be files or directories in your local repository that you don't want to include in the remote, like data, secret keys, configuration files, or virtual environments. Files and directories that should be ignored by Git can be added to a file called `.gitignore` in the main directory of your local repo. Each line in the `.gitignore` is a pattern for the types of files or directories that should be excluded from Git. For instance, `*.csv` will exclude all CSV files, and `venv/` will exclude the virtual environment. For more info on `.gitignore` and how to use patterns to indicate types of files, [read the docs](https://git-scm.com/docs/gitignore). Also, check out the [`.gitignore` file for the data-engineering-bootcamp repository](https://github.com/datastackacademy/data-engineering-bootcamp/blob/main/.gitignore) for a thorough example. For most of the projects in this bootcamp, your `.gitignore` will only need to include your virtual environment and data files. If you like, you can find a thorough boilerplate `.gitignore` and use the same one every time.

`.gitignore`, `README.md`, and  `requirements.txt` are naming conventions, so don't change 'em. Remember the `.` in `.gitignore`.

You can see examples of these files in the [example_files](./example_files) folder of this episode. The `.gitignore` is from [GitHub's collection of gitignore templates](https://github.com/github/gitignore).

</br>

## Project Setup Practice
This short exercise will just practice setting up a weekly code review repository. 

We recommend the flow of:
1. Making the repo and files locally
2. Activating the virtual environment and installing requirements
3. Initializing a Git Repository
4. Writing, saving, and commiting changes to the local files
5. Creating a remote repository on GitHub and pushing the local repository to it

Step 4 and pushing changes will be repeated for as long as you're working on the project. We'll look at all the steps in more detail below.

### Step 1: Make the Repo and Files
- Start a new repo in VS Code. You can call it whatever you want, and delete it later. Include:
- A `REAME.md` with whatever you'd like
- A `requirements.txt` file with `jupyterlab` version 3.3.2 (just like the one in this episode)
- A `.gitignore` file that will ignore your Python virtual environment
- A `practice.ipynb` notebook file, with at least one markdown cell and one code cell. Put whatever you'd like in each of the cells
- A `main.py` file, containing some Python code. In many Python repositories, the code is all contained in `.py` files, rather than notebooks. It's convention to name the file that ties all the other pieces of the project together `main.py`

We recommend practicing terminal commands. Here are the the commands for making folders and files, and opening VS Code.
- In the folder where you'll keep repositories, make a new directory and switch to it:
```
mkdir <dir_name>
cd <dir_name>
```

- Create the files you want:
``` 
touch <file_name> <file_name>
```

- Open VS Code:
```
code .
```

### Step 2: Activate a Virtual Environment and Install Requirements
In the lesson on setting up VS Code, we installed and tested Python's virtualenv, also called "venv". A virtual environment allows you to install specific requirements in an isolated environment, rather than on your main system, so you can use different versions of tools for each project. The `requirements.txt` file lets other developers recreate the same environment you used for the project, so the code runs as expected.

- In the directory of your main project, create a virtual environment:
```
python3.7 -m venv venv
```
You only have to do this once per project. It creates a directory called `venv`. We tell `.gitignore` to exclude this from Git and GitHub, because other developers will make their own.

- Activate the virtual environment:
```
source venv/bin/activate
```
You'll know it works because `(venv)` will appear in the terminal. Activate the virtual environment each time you open a project.

- Install all the packages in the `requirements.txt` file:
```
pip install -r requirements.txt
```
You only have to install the requirements once. They'll be there each time you reactivate the virtual environment for that project.

### Step 3: Initialize a Git Repository

- Initialize a new Git repository, so you can version control the project:
```
git init
```

### Step 4: Make and Commit Changes in the Files

- Put whatever you want in the files, and save the changes.
- Add the files to the Git staging area:
``` 
git add <file_name> <file_name>
```

- Commit the changes:
```
git commit -m "<commit_message>"
```

### Step 5: Create a Remote Repository and Push the Local to It
On your GitHub profile, in the "Repositories" tab, click the green "New" button. Give your new repository a name, then click the green "Create repository" button at the bottom.

You'll be redirected. Follow the commands under the heading "…or push an existing repository from the command line".

If you refresh the GitHub page, you'll see your new repository that reflects the files, code, and commit messages you made on your local repository.

Commit and push your local changes often. It'll make it easier to go back to earlier versions of the project, and will also save your work remotely even if your laptop crashes.

</br>

## Exercise: Solo Project with Branches

Let's practice the same process, but with branches.

Start a new project called "local-trees" and open it in VS Code:
```bash
mkdir local-trees
cd local-trees/
code .
```

Give it a file called `trees.py`:
```bash
touch trees.py
```

We won't install any requirements here, but let's activate a venv anyway, to get into the habit:
```bash
python3.7 -m venv venv
source venv/bin/activate
```

Initialize a new Git repository:
```
git init
```

In `trees.py`, make a list of trees:
```python
trees = ["dogwood", "apple", "cedar"]
```

Don't forget to save the file.
Tell Git to track changes in this file, and commit what you have so far, including a commit message:
```bash
git add trees.py
git commit -m "initial commit"
```

Log into your GitHub account, and create a new repository called "remote-trees"
After you click the green "Create repository" button, follow the instructions under "…or push an existing repository from the command line".
You now have a local and a matching remote!
On your local, create a branch called `more-trees` and switch to it:
```bash
git checkout -b more-trees
```

In your `more-trees` branch, add a few of your favorite trees to your tree list, i.e.
```python
# trees.py
trees = ["dogwood", "apple", "cedar", "cyprus", "oak"]
```

Just like we did above, add the changes and commit them:
```bash
git add trees.py
git commit -m "add a few more trees"
```

Sync your local branch to a corresponding remote branch, and then push the changes branch to branch:
```bash
git push -u origin more-trees
```
> GitHub will automatically create a corresponding remote branch when push a local one. You only need to use `u` the first time you push. This sets your local `more-trees` branch up to track the remote (origin) `more-trees` branch.

GitHub will alert you that your remote `more-trees` branch is now different than your remote `main` branch. Follow the prompts to "Compare and pull request", "Create pull request", and "Merge pull request". Now your `main` branch has your new changes.

But wait! Now your remote `main` has changes that your local `main` doesn't. Switch back to your local `main` branch and pull down the changes:
```bash
git checkout main
git pull origin main
```

...and we're back where we started: a local `main` that matches the remote `main`.

Practice this flow a few more times:
make local branch >> commit changes >> push to remote branch >> open pull request >> merge remote branch with remote main >> pull changes from remote main to local main

</br>

## Other Useful Git Commands

- See what changes have been staged for commit, and which haven't been added yet:
```bash
git status
```
It's useful to look at `git status` before committing, to make sure you're adding only what you want to. It can save you the trouble of trying to remove files from Git later.

- Show changes between the last commit and what you have that isn't commited:
```bash
git diff
```
Actually, you can use `git diff` to compare any two states of your project, like two different commits. See the [Git docs](https://git-scm.com/docs/git-diff) for more options.

- View a history of commits, with the time, commit message, and commit number:
```bash
git log
```

- Show a history of everything you've done in Git on this project, across all branches:
```bash
git reflog
```

- If your project has become a mess and you want to revert it to an earlier state, use `git reflog` to find the `HEAD@{index}` tag for the point in your project's history you want to go back to. Then use that with this command:
```bash
git reset HEAD@{index}
```

- Get rid of all the changes you made since your last commit on a file:
```bash
git restore <file>
```

## Goals for Today
- Learn the tools and flow of GitHub
- Practice the GitHub setup used in Data Stack Academy's weekly code reveiws