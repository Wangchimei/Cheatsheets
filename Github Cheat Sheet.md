# Github Cheat Sheet

## Create
**Creat a new git repository in the directory**  
`git init`

**Clone the entire project into the local directory**  
`git clone <SSH/HTTPS>`

## Local Changes
**View Changed files in your working directory**  
`git status`

**Add all current changes in the directory for the next commit**  
`git add .`  
`git add -A`

**Add a specific file for the next commit**  
`git add <file name>`

**Commit the file changes in staging with description**  
`git commit -m '<Commit message>`

**Change the last commit**  
_Caution: DO NOT amend published commits!_  
`git commit --amend`

**Compare the working directory with index**  
_this shows the changes that are not staged yet._  
`git diff`  
`git diff <file name>` for a specific file

**Compare the working directory with local repository**  
_this shows the list of changes after your last commit._  
`git diff HEAD`  
`git diff HEAD <file name>` for a specific file

**Compare the index with local repository**  
_shows the diff between your last commit and changes to be committed next_  
`git diff --cached`  
`git diff --cached <file name>` for a specific file

## Branches
**View all local and remote branches**  
`git branch -av`

**View all local branches**  
`git branch`

**Create a new branch and switch into it**  
`git checkout -b <branch name>`

**Switch into the specified branch**  
`git checkout <branch name>`

**Delete a specific branch**  
`git branch -d <branch name>`

## View History
**View previous commits, their messages, and ids**  
`git log`

**View who changed a specific file**  
`git log <file name>`

**View who changed a specific file**  
`git blame <file name>`

## Publish
**List all currently configured remotes**  
`git remote -v`

**Add new remote repository with a short name**  
`git remote add <shortname> <url>`

**Download all changes from remote, but don‘t integrate into HEAD**  
`git fetch <remote>`

**Download changes and directly merge/integrate into HEAD**  
`git pull <remote> <branch name>`

**Publish a branch to a remote repository**  
`git push <remote> <branch name>`

**Delete a branch on the remote**  
`git branch -dr <remote/branch name>`

## Merge / Rebase
**Merge a branch into your current HEAD**  
_ensure that you're inside the master branch_  
`git merge <branch name>`

**Rebase your current HEAD onto branch**  
_Caution: DO NOT rebase published commits!_  
`git rebase <branch>`

> While working on a branch you can bring in committed changes from another branch.  
> This is helpful for ensuring that your feature branch can be cleanly merged with the master branch.  
> example: $ git rebase master

### Merge Conflict
* Run `git status` to check where the conflict exists

```ruby
<<<<<<< HEAD
# Current Change
=======
# Incoming Change

> sample incoming change
>>>>>>> a1dfac148fb86311a453a9de338e4d7b9389ade5
```

* Choose what to keep and what to remove

## Undo
**Discard all local changes in your working directory**  
`git reset --hard HEAD`

**Discard local changes in a specific file**  
`git checkout HEAD <file>`

**Revert a commit (by producing a new commit with contrary changes)**  
`git revert <commit>`