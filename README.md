
# 📘 Git Basics: Command Summary and Workflow Explanation

Git is a **distributed version control system (VCS)** that tracks changes in your source code and helps you collaborate with others. Below is a guide to some essential Git commands with explanations of their purpose and behavior in the typical Git workflow.

---

### 🔹 1. `git init`
**Purpose:**  
Initializes an empty Git repository in your current directory.

```bash
git init
```

**Effect:**  
- Converts an ordinary directory into a Git repository.
- Git starts tracking changes in files inside this folder.
- Creates a hidden `.git/` directory where Git stores its metadata (e.g., commits, branches, authors, etc.).

---

### 🔹 2. `git status`
**Purpose:**  
Shows the current state of the working directory and staging area.

```bash
git status
```

**Effect:**  
- Displays which files are **untracked**, **modified**, or **staged**.
- Helps in identifying the next possible Git actions.

---

### 🔹 3. `git add <file>`
**Purpose:**  
Adds a file to the **staging area** (also called the "index") in preparation for a commit.

```bash
git add filename.txt
```

**Effect:**  
- Moves the specified file from "untracked" or "modified" to **staged**.
- Git now knows to include this file in the next commit.

---

### 🔹 4. `git rm --cached <file>`
**Purpose:**  
Removes a file from the staging area (index) but **keeps the file** in the working directory.

```bash
git rm --cached filename.txt
```

**Effect:**  
- Unstages the file if previously added using `git add`.
- File becomes **untracked** again, but not deleted from the system.

---

### 🔹 5. `git commit -m "Your message"`
**Purpose:**  
Creates a snapshot of all staged changes with a descriptive message.

```bash
git commit -m "Initial commit"
```

**Effect:**  
- Files in the staging area become part of the **repository history**.
- These files are now **tracked**, and any further changes will be detected by Git.

> ✅ **Note:** You don’t need to specify a file name with `git commit`. It commits everything in the staging area.

---

### 🔹 6. `git restore <file>`
**Purpose:**  
Restores a file in the working directory to its last committed state.

```bash
git restore filename.txt
```

**Effect:**  
- **Discards** local changes in the file (if modified).
- Reverts the file to the state of the latest commit.
- Useful when you want to undo uncommitted changes.

---

## 🧠 Summary: Git Lifecycle

```
[Untracked] --> git add --> [Staged] --> git commit --> [Tracked]
         ↑                      ↓
  git rm --cached         git restore
```

- **Untracked**: Git sees the file but isn't tracking changes.
- **Staged**: File is ready to be committed.
- **Tracked**: File is part of the repository and its history.

---

## ✅ Example Workflow

```bash
git init
# Initializes repository

git status
# Shows untracked files

git add app.js
# Moves app.js to staged

git status
# Shows app.js as staged

git commit -m "Add app.js file"
# Commits staged file with message

git restore app.js
# Reverts app.js to last committed version

git rm --cached app.js
# Unstages the file, making it untracked
```

---

## 📤 Pushing Code to Remote Repository

You can use either HTTPS or SSH format to push your code to a remote repository like GitHub.

### 🔹 HTTPS Format
```bash
git remote add origin https://github.com/username/repo-name.git
git push -u origin main
```

### 🔹 SSH Format
```bash
git remote add origin git@github.com:username/repo-name.git
git push -u origin main
```

### ✅ Format Comparison
| Use Case                        | Recommended Format |
|-------------------------------|--------------------|
| New user or one-time use       | **HTTPS**          |
| Automation, CI/CD, frequent use| **SSH**            |
| Behind strict firewall         | **HTTPS**          |
| Avoid entering password repeatedly | **SSH**       |

---

Let me know if you'd like to export this as a PDF, or need help with setting up SSH keys or GitHub access tokens.



