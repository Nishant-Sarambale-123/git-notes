Perfect 👍 Now let’s expand **Undo & Reset** into **detailed notes, examples, interview Q\&A, and scenarios**.

---

# 📘 Git Undo & Reset – Detailed Notes

### 1. **`git checkout -- <file>` → Discard changes in file**

* Reverts the file in the **working directory** to the last committed state.
* Example:

  ```bash
  git checkout -- index.html
  ```
* ⚠️ Destroys **uncommitted changes** (can’t be recovered unless stashed).

---

### 2. **`git reset <file>` → Unstage a file**

* Removes file(s) from staging area but keeps changes in working directory.
* Example:

  ```bash
  git add index.html
  git reset index.html   # unstages it
  ```

---

### 3. **`git reset --hard HEAD` → Reset to last commit**

* Moves branch pointer to last commit.
* Removes all staged + working directory changes.
* Example:

  ```bash
  git reset --hard HEAD
  ```
* ⚠️ Irreversible → all uncommitted changes lost.

---

### 4. **`git revert <commit>` → Undo commit by creating a new one**

* Creates a **new commit** that undoes the changes of a previous commit.
* Safe for public/shared branches (doesn’t rewrite history).
* Example:

  ```bash
  git revert a1b2c3d4
  ```
* Commit history remains intact.

---

# 🎤 Git Undo & Reset – Interview Questions

### Basic Level

1. **What is the difference between `git reset` and `git revert`?**

   * `git reset` → moves branch pointer, can discard commits (history rewrite).
   * `git revert` → adds a new commit that undoes changes (history preserved).

2. **How do you discard uncommitted changes in Git?**
   → `git checkout -- <file>` (or `git restore <file>` in newer versions).

3. **How do you unstage a file but keep changes?**
   → `git reset <file>`.

---

### Intermediate Level

1. **What’s the difference between `git reset --soft`, `--mixed`, and `--hard`?**

   * **Soft** → keeps changes staged.
   * **Mixed (default)** → keeps changes in working directory.
   * **Hard** → deletes all changes.

2. **Why is `git revert` preferred over `git reset` in a team environment?**
   → `revert` is safe for shared history since it doesn’t rewrite commits.

3. **What happens internally during `git reset --hard`?**
   → HEAD, branch pointer, staging area, and working directory all move to specified commit.

---

### Advanced Level

1. **How do you recover from a hard reset if you accidentally deleted work?**

   * Use `git reflog` to find lost commit hashes, then `git checkout <hash>` or `git reset --hard <hash>`.

2. **Can you revert multiple commits at once?**
   → Yes:

   ```bash
   git revert <oldest_commit>^..<latest_commit>
   ```

3. **Difference between `git checkout -- <file>` and `git restore <file>`?**

   * `git restore` is the **newer command** (Git ≥ 2.23) for clarity.
   * Both do the same thing (discard working directory changes).

---

# 📌 Scenario-Based Q\&A

### Scenario 1

👉 You staged `index.html` by mistake. How do you unstage it but keep changes?
✅ Run:

```bash
git reset index.html
```

---

### Scenario 2

👉 You made some changes but want to discard them and restore last committed version.
✅ Run:

```bash
git checkout -- file.txt
# or (new syntax)
git restore file.txt
```

---

### Scenario 3

👉 You committed a bug to `main`. You want to **undo it safely** while keeping history.
✅ Run:

```bash
git revert <commit-hash>
```

---

### Scenario 4

👉 You want to remove **all uncommitted changes** and go back to the last commit.
✅ Run:

```bash
git reset --hard HEAD
```

---

### Scenario 5

👉 You accidentally ran `git reset --hard` and lost code. How do you recover?
✅ Use reflog:

```bash
git reflog
git reset --hard <commit-hash>
```

---

⚡ Pro tip: In interviews, they often ask **“If you pushed wrong code to remote, will you use reset or revert?”**
👉 Answer: **Use revert (safe), because reset rewrites history and can break teammates’ repos.**

---

Do you want me to also prepare a **table comparing Reset vs Revert vs Checkout vs Restore** for quick last-minute revision?
