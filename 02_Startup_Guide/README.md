**Developed by Arun VK © 2025**

---

# GitHub Guide Book by Arun VK

## 📑 Table of Contents

1. [Topics Covered](#-topics-covered)
2. [One-Time Git Configuration (Global Setup)](#-one-time-git-configuration-global-setup)
3. [How to Check If Git is Already Configured](#-how-to-check-if-git-is-already-configured)
4. [How to Push Code to GitHub for the First Time](#-how-to-push-code-to-github-for-the-first-time)
5. [How to Push Code to GitHub Thereafter (Subsequent Pushes)](#-how-to-push-code-to-github-thereafter-subsequent-pushes)
6. [Important Git Commands You Should Know](#-important-git-commands-you-should-know)
7. [How to Clone Any GitHub Repo to Your Local System](#-how-to-clone-any-github-repo-to-your-local-system)
8. [How to Get Updated Repo (Keep Cloned Repo Up-to-Date)](#-how-to-get-updated-repo-keep-cloned-repo-up-to-date)
9. [How to Fork a GitHub Repo to Your Personal GitHub](#-how-to-fork-a-github-repo-to-your-personal-github)
10. [The Full Correct Process of How to Work After Fork](#-the-full-correct-process-of-how-to-work-after-fork)
11. [GitHub Pages - Deploy Your Webpage](#-github-pages---deploy-your-webpage)

---

## 📚 Topics Covered

This guide covers:

1. **How to Configure global Git to your local system (ONE TIME PROCESS)**
2. **How to push your code from local to GitHub repo the 1st time**
3. **How to push your code from local to GitHub thereafter (STEP 2 is important for this)**

---

## ⚙️ One-Time Git Configuration (Global Setup)

Configure your Git identity globally on your local system. **This is a ONE TIME process.**

### Commands:

```bash
git config --global user.email "write your email"
git config --global user.name "write your username"
```

### Example:

```bash
git config --global user.email "arunvk@example.com"
git config --global user.name "Arun VK"
```

---

## ✅ How to Check If Git is Already Configured

Check if your email and username are already configured:

### Commands:

| Command | Description | Output |
|---------|-------------|--------|
| `git config --global user.email` | Shows the configured email ID | `arunvk@example.com` |
| `git config --global user.name` | Shows the configured username | `Arun VK` |

---

## 🚀 How to Push Code to GitHub for the First Time

**Everything in brackets `<>` are descriptions you need to replace with actual values!**

### Step-by-Step Process:

1. **Create a GitHub repository** (on GitHub website)

2. **Run these commands in order:**

| Step | Command | Description | Note |
|------|---------|-------------|------|
| 1 | `git init` | Initialize Git in your project folder | **ONE TIME** |
| 2 | `git add .` or `git add <filename>` | Stage all files or specific file | |
| 3 | `git commit -m "commit message"` | Commit your changes with a message | |
| 4 | `git branch -M main` | Change branch to main | **ONE TIME** |
| 5 | `git remote add origin <http..>` | Add your GitHub repo link | **ONE TIME** |
| 6 | `git push -u origin main` | Push to GitHub (main is branch name) | First push |

### Example:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/arunvk/my-project.git
git push -u origin main
```

---

## 🔄 How to Push Code to GitHub Thereafter (Subsequent Pushes)

**After the first time setup, use these commands every time you want to push updates:**

### Commands (in order):

| Step | Command | Description |
|------|---------|-------------|
| 1 | `git status` or `git stat` | Check what files have changed |
| 2 | `git add .` or `git add <filename>` | Stage all changes or specific file |
| 3 | `git commit -m "commit message"` | Commit your changes |
| 4 | `git push` | Push to GitHub |

### Example:

```bash
git status
git add .
git commit -m "Updated navigation bar"
git push
```

---

## 📋 Important Git Commands You Should Know

| Command | Description | When to Use |
|---------|-------------|-------------|
| `git log` | Shows a logbook of what you did - tells you what you were doing all time | View your commit history |
| `git pull` | Pull the updated repo from main | Get latest changes from remote repository |
| `git branch` or `git branch -a` | Shows how many branches are there in a repo | View all branches (local and remote) |
| `git checkout main` | Switches to main branch | Change to main branch |
| `git merge <branch-name>` | Merges specified branch into your current branch (main) | Combine branches together |

### Example:

```bash
# View commit history
git log

# Pull latest updates
git pull

# View all branches
git branch -a

# Switch to main branch
git checkout main

# Merge feature branch into current branch
git merge feature-branch
```

---

## 📥 How to Clone Any GitHub Repo to Your Local System

Clone any repository from GitHub to your local computer.

### Commands:

```bash
git init
git clone <http../link of repo you want to copy>
```

### Example:

```bash
git init
git clone https://github.com/username/repository-name.git
```

---

## 🔃 How to Get Updated Repo (Keep Cloned Repo Up-to-Date)

**Do this when you want an up-to-date repo in your local system:**

### Command:

```bash
git pull
```

**Description:** Pulls latest changes from main branch

### When to Use:

Run this command whenever you want to sync your local repository with the latest changes from the remote repository.

---

## 🍴 How to Fork a GitHub Repo to Your Personal GitHub

**Fork:** You can find this option in another person's repository.

### What is Fork?

- Creates a copy of someone else's repository in YOUR GitHub account
- You can push any file here
- **Won't affect the host/original repository**

### How to Fork:

1. Go to the repository you want to fork
2. Click the **Fork** button (top-right corner)
3. The repository will be copied to your GitHub account

---

## 🛠️ The Full Correct Process of How to Work After Fork

**Follow these steps after forking a repository:**

| Step | Command | Description |
|------|---------|-------------|
| 1 | Create a new folder | Make a new folder for the project |
| 2 | Open Git Bash in that folder | Right-click → Git Bash Here |
| 3 | `git init` | Initialize Git |
| 4 | `git branch -M main` | Change branch to main |
| 5 | `git clone <http../forked repo link>` | Clone your forked repository |
| 6 | By step 5, you will get your full code in that new folder | ✅ |
| 7 | Open the new folder and Git Bash it | Navigate to cloned folder |
| 8 | `git status` | Shows all operations you performed |
| 9 | `git add .` or `git add <filename>` | Stage your changes |
| 10 | `git commit -m "deleted a file"` | Commit with description of operation performed |
| 11 | `git push origin -u main` | Push to your forked repository |

### Complete Example:

```bash
# Step 1-2: Create folder and open Git Bash

# Step 3: Initialize Git
git init

# Step 4: Change to main branch
git branch -M main

# Step 5: Clone forked repo
git clone https://github.com/your-username/forked-repo.git

# Step 6: Navigate to cloned folder
cd forked-repo

# Step 7-8: Check status
git status

# Step 9: Stage changes
git add .

# Step 10: Commit changes
git commit -m "deleted a file"

# Step 11: Push to forked repo
git push origin -u main
```

---

## 🌐 GitHub Pages - Deploy Your Webpage

**GitHub Pages** is used to deploy your webpage and get a live website link (especially useful for web developers).

### How to Use/Access GitHub Pages:

1. Go to your repository on GitHub
2. Click on **Settings**
3. Scroll down to **Pages** section (in the left sidebar)
4. Under **Source**, select the branch you want to deploy (usually `main`)
5. Click **Save**
6. Your website will be live at: `https://your-username.github.io/repository-name/`

### Guide to Access:

```
Settings → Pages → Source → Select Branch (main) → Save
```

### Note:

- Your repository must contain an `index.html` file in the root or docs folder
- GitHub Pages will automatically deploy your site
- You'll receive a live URL where your website is hosted

---

**Developed by Arun VK © 2025**