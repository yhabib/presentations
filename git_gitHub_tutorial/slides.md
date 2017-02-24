include::../_settings_deck.adoc[]
// include::../../_settings_reveal.adoc[]

= Git and GitHub

== Problems we face as a software developers

* How can we manage a large project, when we want to have backups of it at different states?
* Do we save out a copy of the whole project every time we need a backup?
* So everytime we solve a problem in our application, do we make a copy to not break everything with the 
  next changes?
* When working in a team, 
* how can we manage which copy is the __central__ version if each developer works in its own?
* how can we allow for more than one developer to work in the same file?
* how can we track what changes have done everyone?

-

## Version Control Systems (VCS)

> It is a system that records changes to a file or set of files over time
> so that we can recall specific versions later.

It allows to:
* A complete long-term change history of every file. 
  * Creation, edition and deletion of files.
  * Revert files to previous state
  * Revert entire projects back to previous state
  * Compare changes over time
* Branching and mergin
  * Individuals working on independent streams of changes
  * Enables to verify that the changes on each branch do not conflict
* Traceability
  * Trace each change made to the software by each contributor
  * Connect it to project management and bug tracking software such [JIRA]().

------------------------------------

Different flavors:
  * Non-Existing
  * Local, like here
  * Centralized, like there
  * Distributed, like both

![flavors](./resources/flavors.jpeg)


It means that if you screw things up or lose files, you can easily recover them.

------------------------------------

## Git
### What is git?
* By far, the most widely used modern version control system in the world.
* Is a mature, actively maintained open source project originally developed in 2005 by Linus Torvalds(Linux operating system kernel).
* An example of a DVCS 
Rather than having only one single place for the full version history of the software as is common in once-popular version control systems like CVS or Subversion (also known as SVN), in Git, every developer's working copy of 
the code is also a repository that can contain the full history of all changes.
In addition to being distributed, Git has been designed with performance, security and flexibility in mind.

### Strong points of Git 
* Everything is local
* Is really fast
* Snapshots, not diffs
* It is distributed not centralized

------------------------------------

### Installing Git
* **Windows**: [https://git-scm.com/download/win](https://git-scm.com/download/win)
* **Mac**: [https://git-scm.com/download/mac](https://git-scm.com/download/mac)

Then we check the installation by checking git's version: `$ git --version`.

### Configuring Git:
1. Our **identity**, so every time we make a commit, it is associated to our person:
  ```bash
  $ git config --global user.name "your name"
  $ git config --global user.email your.email@propulsion.ch
  ```
2. The **editor** to be used if git wants to show us something:
  ```bash
  git config --global core.editor <vim, emacs, subl, atom....>
  git config --global core.editor "subl -n -w"
  git config --global core.editor "atom --wait" 
  ```
3. Enable **color** in git, so the outputs will be easier to read:
  ```bash
  git config --global color.ui auto
  ```
4. We check the settings:
  ```bash
  git config --list
  ```
------------------------------------

### Git workflow
In a Git repository your files can be in one of these three states:
* Modified: When you modify files in your working directory
* Staged: You stage the files, adding a snapshot of them to the staging area
* Commited: You do a commit that stores snapshot permanently to your GIt directory

![lifecycle](./resources/lifecycle.png)

### Git basic operations
* To create a new Git project:
  * `git init`
  * `git clone /path/to/repo`
* See state of the repository:
  * `git status`
* Add new files to staging area:
  * `git add <filename>`
  * `git add *`
* Commit changes:
  * `git commit -m "Commit message"`
* To see the history of a repo:
  * `git log`
  * `git lop -n <number>`
  * `git log --stat`
  * `git log --pretty=oneline`
* See changes in a commit:
  * `git show <commitID>`
* or compare two commits:
  * `git diff commit1ID commit2ID`
* Revert to previous state:
  * `git checkout <commitID>`
* or return to current state:
  * `git checkout master`

------------------------------------

### Example
1. Create a new repo.
2. Add some files
3. Stage them
4. Modify one file
5. Check state of the repo
6. Commit changes
7. Repeat the process for other files
8. Go back to a previous state.
9. Inspect the directory.

------------------------------------

### Branchhing
Branches are used to develop features isolated from each other:
* The **master** branch is the "default" branch when you create a repository.
* We use other branches for development and merge them back to the master branch upon completition.

![branching](./resources/branching.jpg)

------------------------------------

#### Operations
* To list all branches:
  * `git branch`
* To create a new branch:
  * `git branch <new_branch_name>`
* To switch to a different branch:
  * `git checkout <other_branch_name>`
* To create and swith to a new branch:
  * `git checkout -b <new_branch_name>`
* To delete a branch:
  * `git branch -d <branch_name>`
* To merge branches:
  * `git merge <branch_a> <branch_b>`

------------------------------------

#### Problems
Sometimes auto-merge is not possible and results *conflicts*. So we are responsible to 
merge those conflicts amnally by editing the files shown by git. 
* Editor of choice
* **Tip**: Before mergin changes, preview changes.

------------------------------------

### EXAMPLE 2
* Continuation:
* New branch
  * Commit there
* Generate 

------------------------------------

### Working with remote repositories
#### Operations
* To send these canges to your remote repository:
  * `git push origin master`
* or to a particular branch:
  * `git push origin branch_name`

------------------------------------

#### Origin

When creating a new repository:
* By convention the name it recives the new remote repository(GitHub).
* No requirement ot name the remote repository this way.
* It could be multimple remote repositories.

When cloning a repo for the first time:
* It is the default name fiven to the original remote repository that you clone. It is where
you want to pull and push changes.

------------------------------------

#### Branching
A branch is not available to others unless you push the branch to your remote repository
* `git push origin branch_name`

------------------------------------

## GitHub

------------------------------------


### Tools that make it easier
* Visual Studio code
* Git Desktop
...


## BACKLOG:
* .gitignore
* ./git