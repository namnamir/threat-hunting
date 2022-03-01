
# Concepts
- A **commit** is a record of what changes you have made since the last time you made a commit.
- To add a file to a _commit_, you first need to add it to the **staging** environment.
- **Branches** allow you to move back and forth between 'states' of a project.
- By default, every Git repository’s first **branch** is usually named `master`. Every repository has a primary **branch** that can be thought of as the official version of the repository.
- **Pushing** the _commit_ in a _branch_ to a repository (pushing changes) allows other people to see the changes you've made.
- A **pull request** (or PR) is a way to alert a repo's owners that you want to make some changes to their code.

# Commands
## Initializing a Repository
```bash
### Initialize a Git Repository
### It will initialize and empty Git repository in /path/to/myproject/.git/ on the local system
### A new repository needs to be pushed to the remote repository
git init

### Clone a repository to the local system
git clone <repository_address>
```

### Commiting Changes
```bash
### Add File(s) to a Commit
### Move changes from the working directory to the Git staging area
git add <file_name>

### Create a Commit (including the Message)
git commit -m "Message for the commit."

### Stage All Modified Files to be Committed
git commit -a

### Combination of the Last 2 Options
git commit -am "Message for the commit."

### Update an Existing Commit
### After adding a file and commiting it, we can amend a new commit to it
git commit --amend
```

## Branching
```bash
### See Existing Branches
git branch

### Move to (Check You Out on) an Existing Branch
git checkout <existing_branch_name>

### Create a New Branch
git branch <new_branch_name>

### Create a New Branch and Move to (Check You Out on) it
git checkout -b <new_branch_name>

### Merge <another_branch_name> to the current branch
### If we are currently on the "master" branch, it will merge <another_branch_name> into the "master" one.
git merge <another_branch_name>

### Delete Branches
git branch -d <branch_name>
```

## Pushing Changes to the Repository
```bash
### Push Changes onto a Branch (of the Repository)
### Pushing changes to the <branch_name> branch (the branch on the remote Repository)
git push origin <branch_name>

### Push Changes onto an Existing Branch (of the Repository)
git push -u origin <existing_branch_name>
```

## Pulling Changes from the Repository
```bash
### Get changes on the remote repository to the local repository (update it and merge changes)
git pull origin master

### pull all changes from the remote repository to the local repository
git pull --all
```


## Configuration
```bash
git config --global core.askpass
```

## Status
```bash
### List which files are staged, unstaged, and untracked
git status

### Display committed snapshots
git log
```

##### Sources
- [An Intro to Git and GitHub for Beginners](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)
- [Learn Git with Bitbucket Cloud](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud)
