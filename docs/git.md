[![Home](https://img.shields.io/badge/Home-blue?style=for-the-badge)](https://github.com/Artist-dk/Notes/)
[![References](https://img.shields.io/badge/References-green?style=for-the-badge)](https://github.com/Artist-dk/Notes/blob/master/docs/linux/references.md)



# Configure Git

Set the name that will be attached to your commands.
```
git config --global user.name "Your Name"
```

Set the email that will be attached to your cmmits.
```
git config --global user.email "Your.email@gmail.com"
```
Set the default editor used by Git.
```
git config --global core.editor "code --wait"
```
List all the Git Configurations.
```
git config --list
```

# Getting and creating projects

Create new local repository
```
git init "<project-name>"
```
Clone a repository into a new directory
```
git clone "url"
```
# Basic snapshotting

Add a file to the staging area.
```
git add "file"
```
Add all new and changed files to the staging area.
```
git add
```
Commit changes to the repository with a message.
```
git commit -m "commit-message"
```
Show the status of changes as untracked, modified or staged.
```
git status
```
Show differences between working directory and index.
```
git diff
```
Show difference between the index and the last commit.
```
git diff --staged
```
Unstage a file while retaining changes in working directory.
```
git reset <file>
```
Reset the working directory to the last commit.
```
git reset --hard
```
# Branching and merging
List branches
```
git branch
```
Create a new branch
```
git branch <branch-name>
```
Switch to a branch.
```
git checkout <branch-name>
```
Merge a branch into the current branch
```
git merge <branch-name>
```
Delete a branch
```
git branch -d <branch-name>
```
# Sharing and updating projects
Add a remote repository.
```
git remote add <alise> <url>
```
Fetch changes a remote repository.
```
git fetch <alise>
```
Fetch and merge changes from a remote branch.
```
git pull <alias> <branch>
```
Push a branch to a remote repository and set it as the upstream branch.
```
git push --set-upstream <alise> <branch>
```

# Inspection and comparison

Show the commit history.
```
git log
```
show a graph of the commit hitory.
```
git log --online --graph --decorate --all
```
Show information about a specific commit.
```
git show <commit>
```
Show differences between two commits.
```
git diff <commit1> <commit2>
```

# Undoing changes

Create a new commit that undoes the changes form a previous commit.
```
git revert <commit>
```
Reset the working directory and staging area to match a commit.
```
git reset --hard <commit>
```
Remove untracked files from the working directory.
```
git clean -f
```

# Advanced branching and merging

Reapply commits on top of another base tip .
```
git rebase <branch>
```
Apply the channges introduced by some existing commits.
```
git cherry-pick <commit>
```

# Tagging
List tags
```
git tag
```
Create a new tag.
```
git tag <tag-name>
```
Delete a tag.
```
git tag -d <tag-name>
```
Push tag to a remote repository.
```
git push <alise> <tag-name>
```

# Rewriting history
Modify the most recent commit
```
git commit --amend
```
Interactively rebase commits onto another base.
```
git rebase -i <base>
```

# Submodules 
Add a submodule.
```
git submodule add <url> <path>
```
initialize the submodules.
```
git submodule init 
```
Update the submodules
```
git submodule update
```
