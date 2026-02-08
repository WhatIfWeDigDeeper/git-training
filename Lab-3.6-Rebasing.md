[ProGit](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)

Changing the base of the branch, in other words, the parent of the divergent commit is instead set to the latest commit in main.

Merging vs rebasing

| type | history |
|:---|:-----|
| merge | preserves actual branching |
| rebase | linear history, easier to read |

Database objects in Git are *immutable*.  If you change anything, then you get a different hash.  When rebasing, Git creates new commits, since they have different parents.  The old commits in the branch are orphaned and only reachable by sha (see git reflog).  Git will garbage collect unreachable objects.

### Try it

```bash
# create a feature branch with a couple of commits
git checkout -b feature/rebase-demo
echo "change 1" >> demo.txt && git add . && git commit -m "feature commit 1"
echo "change 2" >> demo.txt && git add . && git commit -m "feature commit 2"

# switch back to main and make a commit
git checkout main
echo "main change" >> main.txt && git add . && git commit -m "main moves forward"

# rebase feature onto main
git checkout feature/rebase-demo
git log --oneline --graph --all   # observe the divergence
git rebase main
git log --oneline --graph --all   # observe the linear history
```

### Warning:  "Do not rebase commits that exist outside your repository." or "Never rebase shared commits"

Why? Because rebase rewrites commit history (new SHAs). Anyone who based work on the original commits will have conflicts.

    # cherry-pick is like a single-commit rebase
    git cherry-pick #sha

---

← [prev](./Lab-3.5-Remote-Branches.md) | [next](./Lab-5.3-Cherry-Picking.md) → | 🏠 [home](./README.md)
