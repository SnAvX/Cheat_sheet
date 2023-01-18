# Git Architecture

## Repository

A set of files, directories, historical records, commits, and heads. Imagine it as a source code data structure, with the attribute that each source code "element" gives you access to its revision history, among other things.

A git repository is comprised of the .git directory & working tree.

## .git Directory (component of repository)

The .git directory contains all the configurations, logs, branches, HEAD, and more.  [Detail list](https://gitready.com/advanced/2009/03/23/whats-inside-your-git-directory.html)

## Working Tree (component of repository)

This is basically the directories and files in your repository. It is often referred to as your working directory.

## Index (component of .git dir)

The Index is the staging area in git. It's basically a layer that separates your working tree from the Git repository. This gives developers more power over what gets sent to the Git repository.

## Commit

A git commit is a snapshot of a set of changes, or manipulations to your Working Tree. For example, if you added 5 files, and removed 2 others, these changes will be contained in a commit (or snapshot). This commit can then be pushed to other repositories, or not!

## Branch

A branch is essentially a pointer to the last commit you made. As you go on committing, this pointer will automatically update to point the latest commit.

##Tag

A tag is a mark on specific point in history. Typically people use this functionality to mark release points (v1.0, and so on)

## HEAD and head (component of .git dir)

HEAD is a pointer that points to the current branch. A repository only has 1 active HEAD. head is a pointer that points to any commit. A repository can have any number of heads.

## Stages of Git

 * Modified - Changes have been made to a file but file has not been committed to Git Database yet
 * Staged - Marks a modified file to go into your next commit snapshot
 * Committed - Files have been committed to the Git Database

# Commande

## init

Create an empty Git repository. The Git repository's settings, stored information, and more is stored in a directory (a folder) named ".git".

```
$ git init
```
## config

To configure settings. Whether it be for the repository, the system itself, or global configurations ( global config file is ~/.gitconfig ).

```
# Print & Set Some Basic Config Variables (Global)
$ git config --global user.email "MyEmail@Zoho.com"
$ git config --global user.name "My Name"
```
Detail comfig [here](https://git-scm.com/docs/git-config)

## help

To give you quick access to an extremely detailed guide of each command. Or to just give you a quick reminder of some semantics.

```
# Quickly check available commands
$ git help

# Check all available commands
$ git help -a

# Command specific help - user manual
# git help <command_here>
$ git help add
$ git help commit
$ git help init
# or git <command_here> --help
$ git add --help
$ git commit --help
$ git init --help
```

## ignore files

To intentionally untrack file(s) & folder(s) from git. Typically meant for private & temp files which would otherwise be shared in the repository.

```
$ echo "temp/" >> .gitignore
$ echo "private_key" >> .gitignore
```

## Status

To show differences between the index file (basically your working copy/repo) and the current HEAD commit.

```
# Will display the branch, untracked files, changes and other differences
$ git status

# To learn other "tid bits" about git status
$ git help status
```

## ad

To add files to the staging area/index. If you do not git add new files to the staging area/index, they will not be included in commits!

```
# add a file in your current working directory
$ git add HelloWorld.java

# add a file in a nested dir
$ git add /path/to/file/HelloWorld.c

# Regular Expression support!
$ git add ./*.java

# You can also add everything in your working directory to the staging area.
$ git add -A
```

This only adds a file to the staging area/index, it doesn't commit it to the working directory/repo.

## branch

Manage your branches. You can view, edit, create, delete branches using this command.

```
# list existing branches & remotes
$ git branch -a

# create a new branch
$ git branch myNewBranch

# delete a branch
$ git branch -d myBranch

# rename a branch
# git branch -m <oldname> <newname>
$ git branch -m myBranchName myNewBranchName

# edit a branch's description
$ git branch myBranchName --edit-description

```

