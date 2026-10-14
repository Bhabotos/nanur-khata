# Nanu's Recipe Book
## OSTAD DevOps Git Assignment

---

## Chapter 1: The First Recipe

### Task A: Git Setup and Repository Initialization

I checked my Git installation using `git --version`. Git version `2.54.0.windows.1` was installed. I verified my global Git username and email, then created the `nanur-khata` folder and initialized it with `git init`.

**Commands used:**

```powershell
git --version
git config --global user.name
git config --global user.email
mkdir nanur-khata
cd nanur-khata
git init
```

### Task B: Creating and Staging the First Recipe

I created `bhapa-pitha.md` with the ingredients and preparation steps for Nanu's bhapa pitha recipe. I checked `git status` and saw that the file was untracked. I then used `git add bhapa-pitha.md` to stage it.

**Commands used:**

```powershell
git status
git add bhapa-pitha.md
git status
```

### Task C: Comparing Git Diff Commands

Nanu corrected the amount of date palm jaggery from two cups to one and a half cups.

I used `git diff` to see the change in my working directory. The output showed that `2 cups` was replaced by `1.5 cups`.

I used `git diff --staged` to inspect the staged version. Before staging the correction, the staged version still contained `2 cups`. After running `git add bhapa-pitha.md` again, the staged version contained `1.5 cups`.

**Commands used:**

```powershell
git diff
git diff --staged
git add bhapa-pitha.md
git diff --staged
```

### Task D: Creating a Meaningful Commit

I committed the bhapa pitha recipe with a meaningful commit message.

```powershell
git commit -m "Add bhapa pitha recipe with corrected gur quantity"
git status
git log --oneline
```

My first commit was `17a3c41`, and Git reported that the working tree was clean after the commit.

### Task E: Unstaging Without Deleting

I created `bazar-list.txt` and staged it accidentally. I used `git reset bazar-list.txt` to unstage it without deleting the file. The file appeared under `Untracked files` in `git status`, and I used `Get-Content bazar-list.txt` to confirm that its content remained available.

**Commands used:**

```powershell
git add bazar-list.txt
git status
git reset bazar-list.txt
git status
Get-Content bazar-list.txt
```

### Chapter 1 Summary

I learned how to initialize a Git repository, create and stage files, compare staged and unstaged changes, create a meaningful commit, and unstage a file without deleting it.

### Evidence

Insert screenshots showing:

1. Git version and configuration.
2. Successful `git init`.
3. `git status` before and after staging.
4. `git diff` and `git diff --staged`.
5. The first commit and clean working tree.
6. `git reset bazar-list.txt` and the file remaining on disk.

---

## Chapter 2: The Secret Spice

### Task A: Creating Secret and Temporary Files

I created `secret-masala.txt`, two temporary files (`recipe.tmp` and `notes.tmp`), and a `draft/` directory to test Git ignore rules.

### Task B: Configuring and Verifying `.gitignore`

I created a `.gitignore` file with these rules:

```gitignore
secret-masala.txt
*.tmp
draft/
```

I verified the rules using `git status --short` and `git status --ignored`. The secret and temporary files were ignored and did not appear in the normal untracked list.

I committed only `.gitignore`, keeping `secret-masala.txt` out of Git tracking.

**Commands used:**

```powershell
Get-Content .gitignore
git status --short
git status --ignored
git add .gitignore
git commit -m "Ignore secret and temporary recipe files"
git log --oneline
```

### What I Learned

`.gitignore` prevents matching untracked files and directories from appearing in Git's normal status list. It helps protect secret and temporary files from accidental inclusion.

### Evidence

Insert screenshots showing:

1. The `.gitignore` contents.
2. `git status --short`.
3. `git status --ignored`.
4. The successful `.gitignore` commit.

---

## Chapter 3: Git Branching and Merging

### Objective

To create a separate branch, add a new recipe, make commits, and merge the branch into the master branch.

### Steps Completed

1. Created a new branch named `eid-special` using `git branch eid-special`.
2. Switched to the branch using `git switch eid-special`.
3. Created `eid-special.md` with an Eid special recipe.
4. Committed the recipe using `git commit`.
5. Added serving tips and created another commit.
6. Switched back to `master` using `git switch master`.
7. Merged the branch using `git merge eid-special`.
8. Verified the commit history using `git log --oneline --graph --all`.

### Verification

After merging, both `master` and `eid-special` pointed to commit `46777a0`. The `eid-special.md` file was included in `master`.

The merge completed successfully using a fast-forward operation. Git moved the `master` branch forward to the latest commit on `eid-special` without creating a separate merge commit.

### Evidence to Capture

Insert screenshots showing:

1. The branch list showing `master` and `eid-special`.
2. Git log before merging, showing the branch commits.
3. Successful output of `git merge eid-special`.
4. Git log after merging, showing both branches at the same commit.
5. Final `git status` output.

### Learning Outcome

I learned how to create and switch branches, make multiple commits, merge changes, and verify Git history.

---

## Overall Assignment Summary

Through these exercises, I practiced essential Git version-control operations, including repository initialization, file staging, comparing changes, committing files, unstaging files, ignoring secret and temporary files, creating branches, and merging changes.

These exercises helped me understand how Git tracks changes and how branches support separate development work.

