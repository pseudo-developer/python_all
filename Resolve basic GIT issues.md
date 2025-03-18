## **Full Workflow to Sync with Remote**
Pull the latest changes:
```git pull origin main```

Resolve conflicts (if any):

If there are conflicts, Git will prompt you to resolve them.

- Open the conflicted files, make the necessary changes, and then stage the resolved files:
```
git add <resolved_file>
Commit the merge (if there were conflicts):
```

```git commit -m "Merge remote changes"```


Push your changes to the remote repository:
```git push origin main```


----

## **Common Issues and Fixes**
### a. Rejected Push (Non-Fast-Forward Error)
This happens when the remote branch has new commits that you don’t have locally.

Solution: Pull the latest changes first, then push again:
```
git pull origin main
git push origin main
```

### b. Untracked Files Causing Issues
If you have untracked files that are causing issues, you can stash them temporarily:
```
git stash
git pull origin main
git stash pop
git push origin main
```

### c. Push to a Different Branch
If you’re working on a feature branch and want to push it to the remote:
```git push origin feature-branch```


----

# Git Workflow Summary: Deleting Files and Syncing with Remote

## What Went Wrong Earlier?

1. **File Deleted Locally but Not Synced:**
   - The file `Scripts/Resolve basic GIT issues.md` was deleted locally but not staged or committed.
   - As a result, the file still existed in the remote repository, causing a mismatch between local and remote.

2. **Git Pull Didn’t Restore the File:**
   - When you ran `git pull origin main`, Git didn’t restore the file because it assumed the local deletion was intentional.

3. **File Visible in Remote but Missing Locally:**
   - The file was visible in the remote repository (e.g., GitHub) but missing in the local repository.

---

## How We Resolved It Using `git reset --hard`

1. **Force-Synced Local Repository with Remote:**
   - Ran the following command to reset the local repository to match the remote repository exactly:
     ```bash
     git reset --hard origin/main
     ```

2. **What Happened During the Reset:**
   - All local changes (staged, unstaged, and untracked) were discarded.
   - The local repository was updated to match the remote repository, restoring the missing file.

3. **File Restored Locally:**
   - After the reset, the file `Scripts/Resolve basic GIT issues.md` was restored in the local repository.

---

## Correct Way to Delete a File and Sync with Remote

To delete a file and ensure the deletion is synced with the remote repository, follow these steps:

### Step 1: Delete the File Using `git rm`
```
git rm Scripts/Resolve\ basic\ GIT\ issues.md
```

### Step 2: Verify the deletion:
```
git status
```
Ensure the file is listed under Changes to be committed.

### Step 3: Commit the Deletion:
```git commit -m "Remove Resolve basic GIT issues.md from Scripts/"```

### Step 4: Push the Changes to Remote:
```git push origin main```

### Step 5: Verify the Remote Repository
Check the remote repository (e.g., GitHub) to confirm the file has been deleted.

