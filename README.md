# GitHub Collaboration & Contribution Workflow

---

## Introduction

Modern software engineering is fundamentally collaborative. Whether you are working in a startup, enterprise company, freelance team, or open-source ecosystem, understanding Git and GitHub collaboration workflow is mandatory.

This documentation provides a complete practical guide for:

- Working on team projects
- Managing source code professionally
- Collaborating through Pull Requests
- Contributing to open-source repositories
- Maintaining clean Git history
- Handling conflicts and synchronization
- Following industry-standard branching strategies

---

## Table of Contents

1. [Git Fundamentals](#1-git-fundamentals)
2. [GitHub Collaboration Architecture](#2-github-collaboration-architecture)
3. [Installing & Configuring Git](#3-installing--configuring-git)
4. [SSH Authentication Setup](#4-authentication-setup-using-ssh)
5. [Creating Personal Repositories](#5-creating-personal-repository)
6. [Forking Existing Repositories](#6-forking-existing-repositories)
7. [Adding Collaborators](#7-adding-collaborators)
8. [Branch Workflow](#8-branch-workflow)
9. [Feature Development Workflow](#9-feature-development-workflow)
10. [Professional Commit Standards](#10-professional-commit-standards)
11. Push Workflow
12. Pull Request Workflow
13. Syncing Forks with Upstream
14. Merge Conflict Resolution
15. Pull & Fetch Workflow
16. Stashing Changes
17. Undo & Recovery Operations
18. Branch Cleanup
19. Professional Team Workflow
20. Real Industry Simulation
21. Best Practices
22. Advanced Git Commands

---

## 1. Git Fundamentals

### What is Git?

Git is a distributed `version control` system developed to track changes in source code during software development.

Git allows developers to:

- Maintain version history
- Collaborate with teams
- Roll back to previous versions
- Track contributions
- Create isolated feature branches
- Merge changes safely

### Why Git is Important

Without Git:

- Collaboration becomes chaotic
- Code overwrites happen frequently
- Tracking bugs becomes difficult
- Deployment pipelines break easily

Git solves these problems by providing:

- Version tracking
- Branching system
- Safe collaboration
- History management
- Recovery mechanisms

---

## 2. GitHub Collaboration Architecture

Git is the version control system.

GitHub is the cloud platform where repositories are hosted.

### Standard Collaboration Flow

```text
Developer Machine (Computer)
       ↓
Local Repository
       ↓
Remote Repository (GitHub)
       ↓
Pull Request
       ↓
Code Review
       ↓
Merge to Main Branch
```

### Important Terminologies

| Term         | Meaning                          |
| ------------ | -------------------------------- |
| Repository   | Project storage                  |
| Commit       | Snapshot of changes              |
| Branch       | Isolated development line        |
| Remote       | Online repository                |
| Origin       | Your repository                  |
| Upstream     | Original repository              |
| Pull Request | Request to merge changes         |
| Fork         | Personal copy of another repo    |
| Merge        | Combining code                   |
| Rebase       | Rewriting commit history cleanly |

---

## 3. Installing & Configuring Git

### Install Git

Download Git:

https://git-scm.com/downloads

### Verify Installation

```bash
git --version
```

### Configure Git Globally

#### Set Username

```bash
git config --global user.name "Your Name"
```

#### Set Email

```bash
git config --global user.email "your-email@example.com"
```

#### Verify Configuration

```bash
git config --list
```

---

## 4. Authentication Setup Using SSH

### Generate SSH Key

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

### Start SSH Agent

```bash
eval "$(ssh-agent -s)"
```

### Add SSH Key

```bash
ssh-add ~/.ssh/id_ed25519
```

### Copy SSH Public Key

```bash
cat ~/.ssh/id_ed25519.pub
```

### Add SSH Key to GitHub

Go to:

https://github.com/settings/keys

### Test SSH Connection

```bash
ssh -T git@github.com
```

---

## 5. Creating Personal Repository

### Create Repository on GitHub

Example:

```text
repo.new → project-name
```

### Navigate Into Project

```bash
cd project
```

### Initialize Project

```bash
npm init -y
```

### Create README

```bash
touch README.md
```

### Stage Changes

```bash
git add .
```

### Commit Changes

```bash
git commit -m "init: Initial project setup"
```

### Push Code

```bash
git push origin main
```

#### OR,

## Cloning Shared Repository

### Clone Repository

#### SSH:

```bash
git clone git@github.com:username/project.git
```

#### HTTPS:

```bash
git clone https://github.com/username/project.git
```

![Clone Repository](images/clone-repository.png)

## Navigate into Project

```bash
cd project
```

## Pull Latest Main Branch

```bash
git checkout main
git pull origin main
```

---

## 6. Forking Existing Repositories

### Clone Your Fork

![Fork Repository](images/fork-repository.png)

```bash
git clone git@github.com:username/project.git
```

### Add Upstream Remote

```bash
git remote add upstream https://github.com/original-owner/project.git
```

### Verify Remotes

```bash
git remote -v
```

---

# 7. Adding Collaborators

### Why Collaborators Matter

Collaborators allow multiple developers to:

- Push code
- Create branches
- Review Pull Requests
- Collaborate efficiently

### Add Collaborator

Navigate to:

```text
Repository → Settings → Collaborators and teams
```

Click:

```text
Add people
```

![Add  Collaborators](images/add-collaborators.png)

#### Search GitHub username or email.

Example:

```text
touhidcodes
```

Click:

```text
Add collaborator
```

![Add  People](images/add-people.png)

### Collaborator Accepts Invitation

After accepting the invitation, collaborators gain repository access.

---

## 8. Branch Workflow

### Never Work Directly on Main

Always create feature branches.

### Create Feature Branch

```bash
git checkout -b feature/login-page
```

#### OR,

```bash
git switch -c feature/login-page
```

### Check Current Branch

```bash
git branch
```

### Branch Naming Convention

```text
feature/user-authentication
feature/payment-system
fix/navbar-overflow
refactor/api-service
docs/setup-guide
```

---

## 9. Feature Development Workflow

### Develop Features

Example tasks:

- Create APIs
- Build UI
- Add validation
- Write tests

### Check Changes

```bash
git status
```

### Stage Files

```bash
git add .
```

#### OR,

### Stage Specific File

```bash
git add src/auth/login.ts
```

### Commit Changes

```bash
git commit -m "feat: add login page functionality"
```

---

## 10. Professional Commit Standards

### Bad Commit Messages

```text
updated code
done
final work
```

### Good Commit Examples

```text
feat: implement JWT authentication
fix: resolve navbar responsiveness
docs: update installation guide
ref: optimize payment service
```

---

# 11. Push Workflow

## Push Feature Branch

```bash
git push origin feature/login-page
```

---

# 11. Pull Request Workflow

## PR Workflow

```text
Developer
   ↓
Push Feature Branch
   ↓
Create Pull Request
   ↓
Code Review
   ↓
Approve Changes
   ↓
Merge PR
```

---

# 12. Syncing Fork with Upstream

## Fetch Upstream Changes

```bash
git fetch upstream
```

---

## Merge Upstream Main

```bash
git checkout main
git merge upstream/main
git push origin main
```

---

# 13. Rebase Feature Branch

```bash
git checkout feature/login-page
git rebase main
```

---

# 14. Merge Conflict Resolution

## Conflict Example

```text
<<<<<<< HEAD
Your Code
=======
Incoming Code
>>>>>>> main
```

---

## Continue Rebase

```bash
git add .
git rebase --continue
```

---

## Abort Rebase

```bash
git rebase --abort
```

---

# 15. Pull vs Fetch

## Fetch

```bash
git fetch
```

Downloads changes without merging.

---

## Pull

```bash
git pull origin main
```

Downloads and merges changes.

---

# 16. Stashing Changes

## Save Changes

```bash
git stash
```

---

## Restore Changes

```bash
git stash pop
```

---

# 17. Undo & Recovery

## Remove Last Commit but Keep Changes

```bash
git reset --soft HEAD~1
```

---

## Remove Last Commit Completely

```bash
git reset --hard HEAD~1
```

---

## Restore File

```bash
git restore filename
```

---

# 18. Branch Cleanup

## Delete Local Branch

```bash
git branch -d feature/login-page
```

---

## Delete Remote Branch

```bash
git push origin --delete feature/login-page
```

---

# 19. Professional Team Workflow

```text
1. Pull latest main branch
2. Create feature branch
3. Develop feature
4. Commit changes
5. Push branch
6. Create Pull Request
7. Code review
8. Fix review comments
9. Merge PR
10. Delete feature branch
```

---

# 20. Real Industry Contribution Simulation

## Workflow

```text
Fork Repository
      ↓
Clone Fork
      ↓
Add Upstream
      ↓
Create Feature Branch
      ↓
Develop Feature
      ↓
Commit Changes
      ↓
Push Branch
      ↓
Create Pull Request
      ↓
Merge Successfully
```

---

# 21. Advanced Git Commands

## View Commit History

```bash
git log --oneline --graph --all
```

---

## Rename Branch

```bash
git branch -m old-name new-name
```

---

## Cherry Pick Commit

```bash
git cherry-pick commit-id
```

---

## View Remote Details

```bash
git remote show origin
```

---

# 22. Best Practices

- Never push directly to `main`
- Use meaningful commit messages
- Pull latest changes before working
- Keep PRs small and focused
- Never commit `.env` or secrets
- Use `.gitignore` properly
- Review code before pushing

---

# Example .gitignore

```gitignore
node_modules
.env
dist
build
coverage
```

---

# Recommended Resources

- https://git-scm.com/doc
- https://docs.github.com/en
- https://learngitbranching.js.org/
- https://www.conventionalcommits.org/en/v1.0.0/

---

# Final Summary

After completing this guide, learners should confidently be able to:

- Create repositories
- Fork projects
- Clone repositories
- Create feature branches
- Commit professionally
- Push safely
- Create Pull Requests
- Sync upstream repositories
- Resolve merge conflicts
- Collaborate professionally in development teams
