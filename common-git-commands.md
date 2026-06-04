# Comprehensive Git Commands Cheat Sheet

A categorized reference guide for the most commonly used Git commands.

---

## Table of Contents

1. [Setup & Configuration](#1-setup--configuration)
2. [Managing Branches](#2-managing-branches)
3. [The Staging & Committing](#3-the-staging--committing)
4. [Sharing & Syncing (Remotes)](#4-sharing--syncing-remotes)
5. [Merging & Rebasing](#5-merging--rebasing)
6. [Inspecting History & Logs](#6-inspecting-history--logs)
7. [Stashing (Temporary Storage)](#7-stashing-temporary-storage)
8. [Undoing Mistakes & Resetting](#8-undoing-mistakes--resetting)

---

## 1. Setup & Configuration

Initialize new repositories or configure your local Git environment.

### Initialize a new local Git repository

```bash
git init
```

### Clone an existing remote repository

```bash
git clone <repository-url>
```

### Set your global username

```bash
git config --global user.name "Your Name"
```

### Set your global email address

```bash
git config --global user.email "your.email@example.com"
```

### List all current configuration settings

```bash
git config --list
```

---

## 2. Managing Branches

Manage, switch, and organize different lines of development.

### List all local branches (\* indicates current branch)

```bash
git branch
```

### List both local and remote branches

```bash
git branch -a
```

### Create a new branch

```bash
git branch <branch-name>
```

### Switch to an existing branch

```bash
git checkout <branch-name>
```

### OR (Modern alternative)

```bash
git switch <branch-name>
```

### Create a new branch and switch to it immediately

```bash
git checkout -b <branch-name>
```

### OR (Modern alternative)

```bash
git switch -c <branch-name>
```

### Delete a local branch (only if safely merged)

```bash
git branch -d <branch-name>
```

### Force delete a local branch (even if unmerged)

```bash
git branch -D <branch-name>
```

### Delete a remote branch

```bash
git push origin --delete <branch-name>
```

---

## 3. The Staging & Committing

Track, stage, and save modifications to your project history.

### Check the status of your working directory (tracked/untracked files)

```bash
git status
```

### View the exact line-by-line changes in unstaged files

```bash
git diff
```

### Stage a specific file for the next commit

```bash
git add <file-name>
```

### Stage ALL changed and new files

```bash
git add .
```

### Unstage a file keeping its changes in the working directory

```bash
git reset <file-name>
```

### Commit staged changes with a descriptive message

```bash
git commit -m "Your descriptive commit message"
```

### Amend the last commit (change message or add forgotten files)

```bash
git commit --amend -m "New updated commit message"
```

## 4. Sharing & Syncing (Remotes)

Connect your local repository to remote servers like GitHub, GitLab, or Bitbucket.

### List all configured remote repositories

```bash
git remote -v
```

### Add a new remote repository link

```bash
git remote add origin <repository-url>
```

### Download history and updates from remote without merging

```bash
git fetch
```

### Fetch updates and immediately merge them into your current branch

```bash
git pull origin <branch-name>
```

### Upload your local commits to the remote repository

```bash
git push origin <branch-name>
```

### Push a new branch and set it to track the remote branch automatically

```bash
git push -u origin <branch-name>
```

## 5. Merging & Rebasing

Integrate changes from one branch into another.

### Merge a target branch into your current active branch

```bash
git merge <branch-name>
```

### Abort a merge in case of complicated conflicts

```bash
git merge --abort
```

### Reapply commits from current branch on top of another base tip

```bash
git rebase <branch-name>
```

### Abort an ongoing rebase operation

```bash
git rebase --abort
```

## 6. Inspecting History & Logs

Review the project's commit history and timeline.

### View the commit history in chronological order

```bash
git log
```

### View a condensed, single-line version of the commit history

```bash
git log --oneline
```

### View commit history as a visual graph diagram

```bash
git log --oneline --graph --all
```

### Show details and content changes of a specific commit

```bash
git show <commit-hash>
```

## 7. Stashing (Temporary Storage)

Shelve dirty working directory changes to work on something else, then bring them back later.

### Save your uncommitted changes to a temporary shelf

```bash
git stash
```

### Save uncommitted changes and include a descriptive label

```bash
git stash save "Working on login logic"
```

### List all saved stashes

```bash
git stash list
```

### Apply the most recent stash and remove it from the stash list

```bash
git stash pop
```

### Apply a specific stash from the list without deleting it

```bash
git stash apply stash@{X}
```

### Discard the most recent stash

```bash
git stash drop
```

## 8. Undoing Mistakes & Resetting

Fix errors, revert commits, or reset files to a clean state.

### Discard changes in a specific file (revert to last commit)

```bash
git checkout -- <file-name>
```

### Create a new commit that completely undoes the effects of an old commit

```bash
git revert <commit-hash>
```

### Undo commits BUT keep your changes staged in the working directory

```bash
git reset --soft HEAD~1
```

### Undo commits AND completely delete all code changes since that point (CAUTION)

```bash
git reset --hard HEAD~1
```
