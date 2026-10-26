# Git & GitHub Workshop: Commands Cheat Sheet

*Or: how to stop naming files `final_v7_REAL_this_one.docx`*

Speaker: **Saraansh Gandhi**

- GitHub: https://github.com/Saraansh0001
- LeetCode: https://leetcode.com/u/SaraanshG
- LinkedIn: https://www.linkedin.com/in/saraansh-gandhi-845403327/

---

## 1. Git vs GitHub

| | Git | GitHub |
|---|---|---|
| What is it? | A tool installed on **your laptop** | A **website** that hosts Git projects |
| What does it do? | Tracks every change to your files | Stores, shares and lets you collaborate |
| Needs internet? | No, works offline | Yes |
| Made by | Linus Torvalds (2005) | Launched 2008, owned by Microsoft since 2018 |
| Analogy | Git = the camera | GitHub = Instagram |

---

## 2. The Big Picture (the workflow)

```
 Working Folder  --git add-->  Staging Area  --git commit-->  Local Repo  --git push-->  GitHub
  (messy desk)               (packing the suitcase)        (sealed, labeled box)       (cloud warehouse)
```

- `git add` = pack it
- `git commit` = seal and label it
- `git push` = ship it

---

## 3. Command Reference

### Step 0: Setup (do this once per laptop)

| Command | What it does |
|---|---|
| `git --version` | Checks that Git is installed |
| `git config --global user.name "Your Name"` | Tells Git who you are (your name appears on commits) |
| `git config --global user.email "you@mail.com"` | Sets your email. Use the same one as your GitHub account |
| `git config --list` | Shows all your current Git settings |
| `git config --global init.defaultBranch main` | Makes new repos start with a branch called `main` |

`--global` means the setting applies to every project on this laptop.

### Step 1: Create a repository

| Command | What it does |
|---|---|
| `mkdir my-first-repo` | Creates a new folder |
| `cd my-first-repo` | Moves into that folder |
| `git init` | Turns the folder into a Git repo by creating a hidden `.git` folder (the brain of your project) |

Run `git init` **once per project**. If you delete the `.git` folder, the project loses all its history.

### Step 2: Stage your changes

| Command | What it does |
|---|---|
| `git status` | Shows what changed. Red = untracked/unstaged, green = staged |
| `git add index.html` | Stages one file |
| `git add images/` | Stages a whole folder |
| `git add .` | Stages everything in the current folder. Check for passwords and `.env` files first! |

### Step 3: Commit (save a snapshot)

| Command | What it does |
|---|---|
| `git commit -m "Add homepage"` | Saves the staged changes as a snapshot with a message |
| `git log --oneline` | Shows your commit history, one line per commit |

Good commit messages complete the sentence "This commit will...":

- Good: `Add login button`, `Fix navbar on mobile`, `Update README`
- Bad: `fixed stuff`, `asdfgh`, `final final pls work`

### Step 4: Push to GitHub

First create an **empty** repository on github.com (no README, no license) and copy its URL.

| Command | What it does |
|---|---|
| `git remote add origin https://github.com/you/my-first-repo.git` | Connects your local repo to GitHub. `origin` is just a nickname for the URL |
| `git branch -M main` | Renames your current branch to `main` |
| `git push -u origin main` | Uploads your commits to GitHub. `-u` remembers the link, so next time `git push` is enough |

If Git asks you to log in, use the browser login or a Personal Access Token, not your GitHub password.

### master vs main

`master` was the old default branch name. GitHub switched new repos to `main` in 2020, and Git added the `init.defaultBranch` setting in version 2.28. It is the same idea with a new name. If an old tutorial says `master`, read it as `main`.

---

## 4. Branching

### Why use branches?

1. **Protect main**: break things on your branch, not in production.
2. **Teamwork**: 5 people, 1 project, 0 fights.
3. **Experiments**: try a wild idea, delete it if it flops.
4. **Code review**: Pull Requests let friends check your work.

### Branching in one picture

```
main:             o-----o---------------------o-----o
                         \                   /
feature/login:            o-----------------o
                       (branch off)     (merge back)
```

Main stays safe while you experiment, then you merge when it works.

### Branch commands

| Command | What it does |
|---|---|
| `git branch` | Lists all branches (the current one has a `*`) |
| `git branch new-idea` | Creates a branch called `new-idea` |
| `git switch new-idea` | Moves you onto that branch |
| `git switch -c new-idea` | Creates the branch **and** moves you onto it |
| `git checkout -b new-idea` | Older way of doing the same as `switch -c` |
| `git push -u origin new-idea` | Uploads the branch to GitHub |
| `git switch main` | Goes back to `main` |
| `git merge new-idea` | Combines `new-idea` into the branch you are on (run it from `main`) |
| `git branch -d new-idea` | Deletes the branch after it has been merged |

Magic trick: make a new file on a branch, switch to `main` and watch it disappear. Switch back and it returns.

---

## 5. Quick Cheat Sheet

```bash
# Setup (once)
git config --global user.name "Your Name"
git config --global user.email "you@mail.com"

# Start a project
git init
git status
git add .
git commit -m "Your message"

# Send it to GitHub
git remote add origin <your-repo-url>
git branch -M main
git push -u origin main

# Branching
git branch
git switch -c name
git switch main
git merge name
git log --oneline
git branch -d name
```

---

## 6. Pop Quiz

1. You edited a file and want to pack it in the suitcase. **Answer: `git add`**
2. Your commits are ready. Ship them to GitHub! **Answer: `git push`**
3. Create a new branch and jump onto it. **Answer: `git switch -c`**

---

## 7. Hands-on Challenge

1. `git init` a new folder
2. Create `README.md`, then `git add` and `git commit`
3. Create a repo on GitHub and `git push` to `main`
4. `git switch -c your-name`, edit a file, commit
5. `git push -u origin your-name`
6. Show your branch on GitHub!

---

## 8. Common Problems

| Problem | Likely fix |
|---|---|
| `nothing to commit` | You forgot `git add`, or nothing changed |
| `remote origin already exists` | You already added it. Check with `git remote -v` |
| `failed to push` / login error | Log in through the browser or use a Personal Access Token |
| `fatal: not a git repository` | You are in the wrong folder, or forgot `git init` |
| Wrong remote URL | Fix it with `git remote set-url origin <correct-url>` |

---

Happy committing! Use your powers for good commits.


<h1> hiii how r u </h1>