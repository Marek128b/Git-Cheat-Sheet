# Git Cheat Sheet

**table of content**
- [Git Cheat Sheet](#git-cheat-sheet)
  - [Git configuration](#git-configuration)
  - [Starting A Project](#starting-a-project)
  - [Day-To-Day Work](#day-to-day-work)
  - [Synchronizing repositories](#synchronizing-repositories)
  - [Git branching model](#git-branching-model)
  - [Tagging known commits](#tagging-known-commits)
  - [Reverting changes](#reverting-changes)
  - [My Strategy](#my-strategy)

## Git configuration
`$ git config --global user.name “Your Name”` <br>
Set the name that will be attached to your commits and tags.<br>
`$ git config --global user.email “you@example.com”` <br>
Set the e-mail address that will be attached to your commits and tags.

## Starting A Project
`$ git init [project name]` <br>
Create a new local repository. If **project name** is provided, Git will
create a new directory name **project name** and will initialize a
repository inside it. If **project name** is not provided, then a new
repository is initialized in the current directory.<br>
`$ git clone [project url]` <br>
Downloads a project with the entire history from the remote repository. <br>

## Day-To-Day Work
`$ git status` <br>
Displays the status of your working directory. Options include new,
staged, and modified files. It will retrieve branch name, current commit
identifier, and changes pending commit. <br>
`$ git add [file]` <br>
Add a **file** to the staging area. Use in place of the full file path to add all
changed files from the current directory down into the directory tree. <br>
`$ git commit -m "[message]"` <br>
Create a new commit from changes added to the staging area.
The commit must have a **message**! <br>

## Synchronizing repositories
`$ git fetch [remote]` <br>
Fetch changes from the **remote**, but not update tracking branches. <br>
`$ git pull [remote]` <br>
Fetch changes from the **remote** and merge current branch with its
upstream. <br>
`$ git push [--tags] [remote]` <br>
ush local changes to the **remote**. Use **--tags** to push tags. <br>
`$ git push -u [remote] [branch]` <br>
Push local **branch** to **remote** repository. Set its copy as an upstream. <br>

## Git branching model
`$ git branch [-a]` <br>
List all local branches in repository. With **-a**: show all branches
(with remote). <br>
`$ git branch [branch_name]` <br>
Create new branch, referencing the current HEAD. <br>
`$ git checkout [-b][branch_name]` <br>
Switch working directory to the specified branch. With **-b**: Git will
create the specified branch if it does not exist. <br>
`$ git merge [from name]` <br>
oin specified `[from name]` branch into your current branch (the one
you are on currently). <br>
`$ git branch -d [name]` <br>
Remove selected branch, if it is already merged into any other.
-D instead of -d forces deletion. <br>

## Tagging known commits
`$ git tag` <br>
List all tags. <br>
`$ git tag [name] [commit sha]` <br>
Create a tag reference named **name** for current commit. `[Add commit
sha]` to tag a specific commit instead of current one. <br>
`$ git tag -a [name] [commit sha` <br>
Create a tag object named **name** for current commit.

## Reverting changes
`$ git reset [--hard] [target reference]` <br>
Switches the current branch to the **target reference**, leaving
a difference as an uncommitted change. When **--hard** is used,
all changes are discarded.
`$ git revert [commit sha]` <br>
Create a new commit, reverting changes from the specified commit.
It generates an inversion of changes. <br>

## My Strategy
![image](02%20Feature%20branches.svg)
