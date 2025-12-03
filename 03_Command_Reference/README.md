**Developed by Arun VK © 2025**

---

# Git & GitHub Commands Reference Guide

## 📑 Index

1. [Git Configuration Commands](#1-git-configuration-commands)
2. [Repository Initialization Commands](#2-repository-initialization-commands)
3. [Staging & Committing Commands](#3-staging--committing-commands)
4. [Branching Commands](#4-branching-commands)
5. [Merging Commands](#5-merging-commands)
6. [Remote Repository Commands](#6-remote-repository-commands)
7. [Undoing / Fixing Mistakes](#7-undoing--fixing-mistakes)
8. [Git Logs & Repo History](#8-git-logs--repo-history)
9. [GitHub Authentication Commands](#9-github-authentication-commands)
10. [GitHub Forking Commands](#10-github-forking-commands)
11. [Tagging & Release Commands](#11-tagging--release-commands)
12. [GitHub Pages Commands](#12-github-pages-commands)
13. [Git Aliases](#13-git-aliases)
14. [Troubleshooting Commands](#14-troubleshooting-commands)

---

## 1. Git Configuration Commands

| Command | Description | When to Use | Example | Reference Output |
|---------|-------------|-------------|---------|------------------|
| `git config --global user.name "Your Name"` | Sets the name attached to your commits | First time Git setup or when changing identity | `git config --global user.name "John Doe"` | (No output) |
| `git config --global user.email "email@example.com"` | Sets the email attached to your commits | First time Git setup or when changing identity | `git config --global user.email "john@example.com"` | (No output) |
| `git config --list` | Lists all Git configuration settings | Verifying your Git configuration | `git config --list` | `user.name=John Doe`<br>`user.email=john@example.com` |
| `git config --global core.editor "code --wait"` | Sets your default text editor for Git | Customizing commit message editor | `git config --global core.editor "vim"` | (No output) |

---

## 2. Repository Initialization Commands

| Command | Description | When to Use | Example | Reference Output |
|---------|-------------|-------------|---------|------------------|
| `git init` | Initializes a new Git repository | Starting a new project locally | `git init` | `Initialized empty Git repository in /path/.git/` |
| `git clone <url>` | Creates a copy of an existing repository | Downloading a project from GitHub | `git clone https://github.com/user/repo.git` | `Cloning into 'repo'...`<br>`done.` |

---

## 3. Staging & Committing Commands

| Command | Description | When to Use | Example | Reference Output |
|---------|-------------|-------------|---------|------------------|
| `git add .` | Stages all changes in the current directory | Preparing all modified files for commit | `git add .` | (No output) |
| `git add <file>` | Stages a specific file | Preparing a single file for commit | `git add index.html` | (No output) |
| `git status` | Shows the status of changes | Checking what files are modified or staged | `git status` | `On branch main`<br>`Changes to be committed:` |
| `git commit -m "message"` | Commits staged changes with a message | Saving staged changes to repository history | `git commit -m "Add login feature"` | `[main a1b2c3d] Add login feature`<br>`1 file changed, 10 insertions(+)` |
| `git commit -am "message"` | Stages and commits all tracked files | Quick commit of all modified tracked files | `git commit -am "Fix bug"` | `[main d4e5f6g] Fix bug`<br>`2 files changed, 5 insertions(+)` |

---

## 4. Branching Commands

| Command | Description | When to Use | Example | Reference Output |
|---------|-------------|-------------|---------|------------------|
| `git branch` | Lists all local branches | Viewing available branches | `git branch` | `* main`<br>`  feature-login` |
| `git branch -a` | Lists all branches (local and remote) | Viewing all branches including remote | `git branch -a` | `* main`<br>`  remotes/origin/main` |
| `git checkout <branch>` | Switches to an existing branch | Moving to a different branch | `git checkout feature-login` | `Switched to branch 'feature-login'` |
| `git checkout -b <branch>` | Creates and switches to a new branch | Starting work on a new feature | `git checkout -b feature-signup` | `Switched to a new branch 'feature-signup'` |
| `git branch -M main` | Renames the current branch | Renaming master to main | `git branch -M main` | (No output) |

---

## 5. Merging Commands

| Command | Description | When to Use | Example | Output |
|---------|-------------|-------------|---------|--------|
| `git merge <branch>` | Merges specified branch into current branch | Combining feature branch into main | `git merge feature-login` | `Updating a1b2c3d..d4e5f6g`<br>`Fast-forward` |
| `git merge --abort` | Aborts the current merge process | Canceling a merge with conflicts | `git merge --abort` | (No output - returns to pre-merge state) |

---

## 6. Remote Repository Commands

| Command | Description | When to Use | Example | Output |
|---------|-------------|-------------|---------|--------|
| `git remote -v` | Lists all remote connections | Viewing configured remote repositories | `git remote -v` | `origin  https://github.com/user/repo.git (fetch)`<br>`origin  https://github.com/user/repo.git (push)` |
| `git remote add origin <url>` | Adds a new remote repository | Connecting local repo to GitHub | `git remote add origin https://github.com/user/repo.git` | (No output) |
| `git remote remove origin` | Removes a remote connection | Disconnecting from a remote repository | `git remote remove origin` | (No output) |
| `git push -u origin main` | Pushes and sets upstream branch | First push to a new remote branch | `git push -u origin main` | `Branch 'main' set up to track remote branch 'main'` |
| `git push` | Pushes commits to remote repository | Uploading local commits to GitHub | `git push` | `To https://github.com/user/repo.git`<br>`a1b2c3d..d4e5f6g  main -> main` |
| `git pull` | Fetches and merges remote changes | Updating local repo with remote changes | `git pull` | `Updating a1b2c3d..d4e5f6g`<br>`Fast-forward` |
| `git fetch` | Downloads remote changes without merging | Checking remote updates before merging | `git fetch` | `remote: Counting objects: 5, done.` |

---

## 7. Undoing / Fixing Mistakes

| Command | Description | When to Use | Example | Output |
|---------|-------------|-------------|---------|--------|
| `git restore <file>` | Discards changes in working directory | Reverting unstaged file modifications | `git restore index.html` | (No output) |
| `git restore --staged <file>` | Unstages a file | Removing file from staging area | `git restore --staged index.html` | (No output) |
| `git reset --soft <commit>` | Resets to commit, keeps changes staged | Undoing commits but keeping changes | `git reset --soft HEAD~1` | (No output) |
| `git reset --hard <commit>` | Resets to commit, discards all changes | Completely removing commits and changes | `git reset --hard HEAD~1` | `HEAD is now at a1b2c3d Previous commit` |
| `git revert <commit>` | Creates new commit that undoes changes | Safely undoing a commit in shared history | `git revert d4e5f6g` | `[main h7i8j9k] Revert "commit message"` |
| `git stash` | Temporarily saves uncommitted changes | Switching branches with unsaved work | `git stash` | `Saved working directory and index state` |
| `git stash pop` | Applies and removes most recent stash | Restoring stashed changes | `git stash pop` | `On branch main`<br>`Changes not staged for commit:` |

---

## 8. Git Logs & Repo History

| Command | Description | When to Use | Example | Output |
|---------|-------------|-------------|---------|--------|
| `git log` | Shows detailed commit history | Viewing full commit history with details | `git log` | `commit d4e5f6g`<br>`Author: John Doe`<br>`Date: Mon Dec 2 10:30:00 2024` |
| `git log --oneline` | Shows condensed commit history | Quick overview of recent commits | `git log --oneline` | `d4e5f6g Add login feature`<br>`a1b2c3d Initial commit` |
| `git reflog` | Shows history of HEAD changes | Recovery of lost commits | `git reflog` | `d4e5f6g HEAD@{0}: commit: Add login`<br>`a1b2c3d HEAD@{1}: commit: Initial` |
| `git show <commit>` | Shows details of a specific commit | Inspecting changes in a particular commit | `git show d4e5f6g` | `commit d4e5f6g`<br>`diff --git a/index.html` |

---

## 9. GitHub Authentication Commands

| Command | Description | When to Use | Example | Output |
|---------|-------------|-------------|---------|--------|
| `ssh-keygen -t rsa -b 4096 -C "email@example.com"` | Generates SSH key pair | Setting up SSH authentication for GitHub | `ssh-keygen -t rsa -b 4096 -C "john@example.com"` | `Generating public/private rsa key pair` |
| `ssh -T git@github.com` | Tests SSH connection to GitHub | Verifying SSH key setup | `ssh -T git@github.com` | `Hi username! You've successfully authenticated` |
| Personal Access Token via HTTPS | Use token instead of password for HTTPS authentication | Authenticating with HTTPS protocol | Use token when Git prompts for password | `Authentication successful` |

---

## 10. GitHub Forking Commands

| Command | Description | When to Use | Example | Output |
|---------|-------------|-------------|---------|--------|
| `git remote add upstream <url>` | Adds original repo as upstream | Contributing to forked projects | `git remote add upstream https://github.com/original/repo.git` | (No output) |
| `git fetch upstream` | Fetches changes from upstream repo | Getting updates from original repository | `git fetch upstream` | `remote: Counting objects: 10, done.` |
| `git merge upstream/main` | Merges upstream changes into local | Syncing fork with original repository | `git merge upstream/main` | `Updating a1b2c3d..d4e5f6g`<br>`Fast-forward` |

---

## 11. Tagging & Release Commands

| Command | Description | Example |
|---------|-------------|---------|
| `git tag` | Lists all tags in repository | `git tag` |
| `git tag <version>` | Creates a lightweight tag | `git tag v1.0.0` |
| `git tag -a <version> -m "message"` | Creates an annotated tag with message | `git tag -a v1.0.0 -m "Release version 1.0.0"` |
| `git push --tags` | Pushes all tags to remote repository | `git push --tags` |

---

## 12. GitHub Pages Commands

| Command | Description | Example |
|---------|-------------|---------|
| Enable via Repository Settings | Navigate to repository settings to enable GitHub Pages | Go to Settings → Pages → Source: Select branch (main) → Save |
| Create `index.html` in root or docs folder | Create landing page file for GitHub Pages | Add `index.html` to root directory or docs folder |
| Push changes to trigger deployment | Commit and push changes to deploy site | `git add .` → `git commit -m "Deploy site"` → `git push origin main` |

---

## 13. Git Aliases

| Command | Description | Example |
|---------|-------------|---------|
| `git config --global alias.s status` | Creates shortcut `git s` for status command | Run `git s` instead of `git status` |
| `git config --global alias.l "log --oneline"` | Creates shortcut `git l` for log command | Run `git l` instead of `git log --oneline` |
| `git config --global alias.co checkout` | Creates shortcut `git co` for checkout | Run `git co main` instead of `git checkout main` |
| `git config --global alias.br branch` | Creates shortcut `git br` for branch | Run `git br` instead of `git branch` |

---

## 14. Troubleshooting Commands

| Problem | Fix |
|---------|-----|
| `fatal: remote origin already exists` | Run `git remote remove origin` then `git remote add origin <url>` |
| `error: failed to push some refs` (non-fast-forward) | Run `git pull origin main --rebase` then `git push` |
| Merge conflict | 1. Open conflicted files and resolve manually<br>2. `git add <resolved-files>`<br>3. `git commit` to complete merge |
| `Permission denied (publickey)` | 1. Generate SSH key: `ssh-keygen -t rsa -b 4096`<br>2. Add to GitHub: Settings → SSH and GPG keys → New SSH key<br>3. Test connection: `ssh -T git@github.com` |
| Accidentally committed to wrong branch | 1. `git log` (find commit hash)<br>2. `git checkout correct-branch`<br>3. `git cherry-pick <hash>`<br>4. `git checkout wrong-branch`<br>5. `git reset --hard HEAD~1` |
| Undo last commit but keep changes | Run `git reset --soft HEAD~1` |
| Completely remove last commit and changes | Run `git reset --hard HEAD~1` |
| Recover deleted branch | 1. `git reflog` (find commit hash)<br>2. `git checkout -b branch-name <commit-hash>` |

---

**Developed by Arun VK © 2025**