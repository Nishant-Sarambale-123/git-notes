Great 👍 You’re systematically building Git notes. Let me expand your **Basic Commands** with **detailed explanations, examples, interview questions, and scenarios**.

---

# 📘 Git Basic Commands – Detailed Notes

### 1. **`git init` → Initialize repo**

* Creates a new **empty Git repository** in the current directory.
* Adds a hidden `.git` folder that stores all version control information.
* Example:

  ```bash
  mkdir myproject && cd myproject
  git init
  ```
* Output: `Initialized empty Git repository in /path/myproject/.git/`

---

### 2. **`git clone <url>` → Copy remote repo**

* Downloads a **full copy (with history)** of a remote repository.
* Example:

  ```bash
  git clone https://github.com/user/project.git
  ```
* Creates a local folder `project/` with code + history.

---

### 3. **`git status` → Check current state**

* Shows:

  * Files **modified**, **staged**, **untracked**.
  * Current branch.
* Example:

  ```bash
  git status
  ```
* Output:

  ```
  On branch main
  Changes not staged for commit:
    modified: index.html
  Untracked files:
    style.css
  ```

---

### 4. **`git add <file>` → Move changes to staging**

* Stages file(s) to be committed.
* Example:

  ```bash
  git add index.html
  git add .    # add all changes
  ```
* Moves changes from **working directory → staging area**.

---

### 5. **`git commit -m "message"` → Save changes**

* Saves a **snapshot** of staged changes in the **local repo**.
* Example:

  ```bash
  git commit -m "Added login feature"
  ```
* Each commit is given a unique **SHA-1 hash**.

---

### 6. **`git log` → Show history**

* Displays commit history with ID, author, date, message.
* Example:

  ```bash
  git log
  ```
* Sample output:

  ```
  commit a1b2c3d4
  Author: Nishant <nishant@email.com>
  Date:   Sat Aug 10 15:42:00 2025
      Added authentication
  ```

---

### 7. **`git diff` → Show file changes**

* Shows line-by-line differences between versions.
* Example:

  ```bash
  git diff            # changes not staged
  git diff --staged   # staged changes
  ```
* Output:

  ```diff
  - old line
  + new line
  ```

---

# 🎤 Git Basic Commands – Interview Questions

### Basic Level

1. **What is the difference between `git init` and `git clone`?**

   * `git init` → start a brand-new repo.
   * `git clone` → copy an existing remote repo.

2. **What happens if you run `git commit` without `git add`?**

   * Only previously staged files are committed. New changes won’t be included.

3. **What’s the difference between `git diff` and `git log`?**

   * `git diff` → shows file content differences.
   * `git log` → shows commit history.

4. **What is the purpose of `git status`?**

   * To check the working directory, staging area status, and branch information.

---

### Intermediate Level

1. **If you run `git add .` vs `git add -A`, what’s the difference?**

   * `git add .` → adds new + modified files in current directory.
   * `git add -A` → adds new + modified + deleted files (entire repo).

2. **Can you commit empty changes in Git?**

   * Yes, using `git commit --allow-empty`.

3. **How do you view changes between two commits?**

   * `git diff <commit1> <commit2>`.

---

# 📌 Scenario-Based Q\&A

### Scenario 1:

👉 You created a new project folder and want to start tracking changes.
✅ Run:

```bash
git init
git add .
git commit -m "Initial commit"
```

---

### Scenario 2:

👉 You cloned a repo but want to check what files you changed before committing.
✅ Use:

```bash
git status
git diff
```

---

### Scenario 3:

👉 You modified `index.html` but forgot whether it’s staged or not.
✅ Run:

```bash
git status
```

(It will show if `index.html` is staged or not).

---

### Scenario 4:

👉 You want to see what exactly changed before staging a file.
✅ Run:

```bash
git diff index.html
```

---

### Scenario 5:

👉 You want to see all commits made by you in last week.
✅ Run:

```bash
git log --author="yourname" --since="1 week ago"
```

---

Would you like me to also prepare a **side-by-side command → purpose → example → output** table for quick last-minute revision?
