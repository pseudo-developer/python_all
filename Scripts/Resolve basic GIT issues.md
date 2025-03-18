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
