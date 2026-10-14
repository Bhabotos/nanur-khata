# Nanu's Recipe Book
## OSTAD DevOps Git Assignment

## Chapter 1: The First Recipe

### Task A: Git Setup and Repository Initialization

I checked my Git installation using `git --version`. Git version 2.54.0.windows.1 was installed. I verified my global Git username and email, then created the `nanur-khata` folder and initialized it with `git init`.

Commands used:

```bash
git --version
git config --global user.name
git config --global user.email
mkdir nanur-khata
cd nanur-khata
git init
```

### Task B: Creating and Staging the First Recipe

I created `bhapa-pitha.md` with the ingredients and preparation steps for Nanu's bhapa pitha recipe. I checked `git status` and saw that the file was untracked. I then used `git add bhapa-pitha.md` to stage it.

Commands used:

```bash
git status
git add bhapa-pitha.md
git status
```

### Task C: Comparing Git Diff Commands

Nanu corrected the amount of date palm jaggery from two cups to one and a half cups.

I used `git diff` to see the change in my working directory. The output showed that `2 cups` was replaced by `1.5 cups`.

I used `git diff --staged` to inspect the staged version. Before staging the correction, the staged version still contained `2 cups`. After running `git add bhapa-pitha.md` again, the staged version contained `1.5 cups`.

Commands used:

```bash
git diff
git diff --staged
git add bhapa-pitha.md
git diff --staged
```

### Task D: Creating a Meaningful Commit

I committed the bhapa pitha recipe with a meaningful commit message.

```bash
git commit -m "Add bhapa pitha recipe with corrected gur quantity"
git status
git log --oneline
```

My first commit was `17a3c41`, and Git reported that the working tree was clean after the commit.

### Task E: Unstaging Without Deleting

I created `bazar-list.txt` and staged it accidentally. I used `git reset bazar-list.txt` to unstage it without deleting the file. The file appeared under `Untracked files` in `git status`, and I used `Get-Content bazar-list.txt` to confirm that its content remained available.

Commands used:

```bash
git add bazar-list.txt
git status
git reset bazar-list.txt
git status
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

Commands used:

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