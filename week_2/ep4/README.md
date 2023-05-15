# GitHub for Collaboration
Now that you know the flow of solo pushing, merging, and pulling, let see where GitHub really shines: working on projects with other people.

When collaborating with a team, good communication can save you a lot of trouble. Scrum meetings are a great time for each person on a development team to say what they'll be working on that day, so people aren't simultaneously changing the same file. Writing useful commit messages will also help communicate your intentions to your peers.

Pair up with a classmate. One person in the pair should clone their partner's "remote-trees" repository from our first GitHub lesson, and name their local version of it `trees-collab`:
```bash
git clone https://github.com/<PARTNER-GITHUB-PROFILE>/remote-trees.git trees-collab
```

Go to that directory, and open the project:
```bash
cd trees-collab
code .
```
Check that the local project is still synched with the remote:
```bash
git remote -v
```
Meanwhile, the person in the pair who owns the GitHub repo should give their partner permissions to push changes to it:
- In the top navigation bar of the GitHub page for the project, click "settings"
- Select "Collaborators" from the left sidebar
- In the "Manage Access" section, click the green "Add people" button
- Search for your partner by name, username, or email, and add them as a collaborator

At this point, both people in the pair have matching local versions of the "remote-trees" repository.
Each person, in your local repo: 
- Make a branch off `main` called `<YOUR-NAME>-edits`.
- Switch to that branch.
- Make a new file called `<YOUR-NAME>-trees.py`
- Add some Python code to your file! Here's and example:
```python
# alma-trees.py
tree-fact = "Dendrochronology is the study of tree rings"
```
- Save your code, commit it, and push your local branch to a corresponding remote branch:
```bash
git push origin `<YOUR-NAME>-edits`
 ```
 - Open a pull request, and ask your partner to review the new code before merging your branch into `main`.
 - Once it's merged, you can delete the branch. You can then both pull the changes from the remote `main` to your local `main`.

 Repeat this three more times with whatever code you'd like.


 ## Merge Conflicts

 When two people are editing the same code simultaneously, you can get a merge conflict. Git doesn't know which version of the code should be used, so you have to comb through the changes and manually select the ones you want. With your pair, let's create a merge conflict and resolve it.

 - Start where you left off from the previous exercise: you and your pair should have matching local repositories, each synched to the same remote, and this repo should have the original `trees.py` file in it.

 Each person in the pair, on your own local repository:
 - Create and switch to a new branch off `main` called `<YOUR-NAME>-conflict`
 - Make some changes to the code that's already in there: remove some trees from the list, and add some different ones. Add whatever other code you'd like to the file.
 - Save and commit your changes.
 - Push your local branch to a corresponding remote branch:
 ```bash
 git push origin `<YOUR-NAME>-conflict`
 ```
 - On GitHub, create a pull request to merge your branch into `main`. Have your partner review it before merging.

 The first person to create a pull request and merge should have no trouble. The second person, however, will run into a merge conflict. This person should share their screen, so you can resolve the conflict together.
 - On GitHub, on the page for the pull request, click the "Resolve conflicts" button
- You'll be directed to a page that looks something like this:
```python
 <<<<<<< alma-conflict
trees = ["pomegranate", "apple", "cedar", "Christmas"]
=======
trees = ["baobob", "apple", "cedar", "poplar"]
>>>>>>> main
```
- Delete the conflict markers (`<<<<<<< alma-conflict`, `=======`, and `>>>>>>> main`)
- From the remaining code, keep the version you want, and delete the other
- Click the "Resolve conflict" button at the top right of the GitHub page
- Click the green "Commit merge" button

Repeat this three more times with whatever code you'd like.

Finish early? Practice the collaborative flow and resolving merge conflicts with your partner. This is a good place to experiment and make mistakes.

GitHub can also be social! If you're looking for some code inspiration, [explore public repositories by topic](https://github.com/topics), or follow your friends and see what kinds of projects they're making.

## Goals for Today
- Practice collaboration on GitHub
- Practice resolving merge conflicts