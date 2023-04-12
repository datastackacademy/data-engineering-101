# Git and GitHub

In today's lesson, we'll be practicing Git and GitHub. These are essential tools for version control, collaboration, and presenting your work. In bootcamp, you'll use Git and GitHub for your weekly code reviews and your team projects. You'll also probably use them in the rest of your data engineering career.

Git is an open source software used for version control. [GitHub](https://github.com/) is the industry standard for using Git to collaborate on development projects, and to store a portfolio of your own projects (projects on GitHub are called repositories, or repos). 

## Make a Profile
If you don't already have a GitHub profile, make one now! Go to [https://github.com/](https://github.com/) and click 'Sign Up', then follow the prompts. 

There are lots of ways to customize your settings, but a basic profile is fine for now.

Take some time to click around on your new GitHub profile to explore the tabs.


## Key Terms

### Remote Repositories and Local Repositories
In the [course-overview section](https://github.com/datastackacademy/data-engineering-bootcamp/blob/main/getting-started/course-overview.md) you saw how to fork a copy of the remote data engineering bootcamp repo. You can think of a local repo as the version of a project you have on your own computer, where you can make changes to share later, and a remote repository as the one on GitHub, seen by everyone. 


### Forking and Cloning
You can also create a local repo from a remote by cloning it. A forked repository is a completely independent copy, while a cloned one is sychronized with the remote.

### Pushing and Pulling
Push changes from local -> remote. Pull changes remote -> local.

> "Remote" means GitHub. "Local" means your personal computer.

### Commit Messages
'Committing' will create a record of your changes in the project's version history. When you commit changes, include a short message of what you did and why. These messages show up in the version history too. Writing useful messages can save you a lot of trouble if you need to troubleshoot later.

By convention, commit messages are written in the present tense.

### Branches, Pull Requests, and Merging
On both the remote and local, the `main` branch is the official version of the project. Creating a branch makes a copy of the project where you can play around and make changes without affecting the `main` branch. 

If you like the changes you made on your local branch, you can push them to a corresponding remote branch and create a pull request. A pull request is a way of asking your collaborators to merge your changes with the remote `main` branch, making them part of the shared, official version of the project.

## Git Flow Basics

Git and GitHub can become quite complex, especially when you're collaborating with others. Today, we'll just practice basic solo projects, like the repositories you'll submit for code reviews in this course.

#### Without Branches
This is the simplest way to use Git. The flow is:
- Make changes to your files in VS Code.
- Save the changes in VS Code.
- In your terminal, use the command `git add <file_name>` to add each changed file to Git's staging area. If the file isn't in your terminal's present working directory, you'll also have to include the relative path.
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

## The .gitignore File

There will often be files or directories in your local repository that you don't want to include in the remote, like data, secret keys, configuration files, or virtual environments. Files and directories that should be ignored by Git can be added to a file called `.gitignore` in the main directory of your local repo. Each line in the `.gitignore` is a pattern for the types of files or directories that should be excluded from Git. For instance, `*.csv` will exclude all CSV files, and `venv/` will exclude the virtual environment. For more info on `.gitignore` and how to use patterns to indicate types of files, [read the docs](https://git-scm.com/docs/gitignore). Also, check out the [`.gitignore` file for the data-engineering-bootcamp repository](https://github.com/datastackacademy/data-engineering-bootcamp/blob/main/.gitignore) for a thorough example. For most of the projects in this bootcamp, your `.gitignore` will only need to include your virtual environment and data files.

It's best practice, when adding files to be committed, to use
```bash
git add <FILE_NAMES>
```
...listing each file. Do NOT add files with `git add *`, which can accidentally include files that ought to be excluded.

## Exercise: Project Setup
Every week, you'll use GitHub to share a repository for your code review project. Nearly all of these will include
- A `requirements.txt` file: you've already seen and used these in this course! It's just a list of the packages that the project in the repository needs to install before it can run. If you include a `requirements.txt` file your user can just run
`pip install -r requirements.txt`
then start running the code in the repo.
- A `README.md` file: you've already seen this, too! It's what shows up on the main page of a GitHub repo. In the Data Stack Academy repository, we use the README to orient you to the content of the each episode. For your code review projects, you'll usually want to include a description of the project, a list of the technologies used, a list of the known bugs, and a diagram of how the pieces in your project fit together.
- A `.gitignore` file: this is discussed above. If you like, you can find a thorough boilerplate `.gitignore` and use the same one every time.

This short exercise will just practice setting up a weekly code review repository. Start a new repo; you can call it whatever you want, and delete it later. Include:
- A `REAME.md` with whatever you'd like
- A `requirements.txt` file with `jupyterlab` version 3.3.2 (just like the one in this episode)
- A `.gitignore` file that will ignore your Python virtual environment
- A `practice.ipynb` notebook file, with at least one markdown cell and one code cell. Put whatever you'd like in each of the cells
- A `main.py` file, containing some Python code. In many Python repositories, the code is all contained in `.py` files, rather than notebooks. It's convention to name the file that ties all the other pieces of the project together `main.py`

## Exercise: Solo Project with Branches

You already know how to share your weekly code review projects on GitHub. Let's practice the same process, but with branches.

Start a new project called "local-trees", initialize a Git repository, and open it in VS Code:
```bash
mkdir local-trees
cd local-trees/
git init
code .
```
Give it a file called `trees.py`:
```bash
touch trees.py
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