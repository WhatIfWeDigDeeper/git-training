# Worktrees

[Git Worktrees](https://git-scm.com/docs/git-worktree) let you check out multiple branches simultaneously in separate directories — no stashing or committing WIP required.

### When are worktrees useful?

- Reviewing a PR while working on your own feature
- Running tests on one branch while editing another
- Comparing behavior across branches side-by-side

### Create a worktree

```bash
# from your main repo directory
git worktree add ../hotfix-dir hotfix/urgent-bug

# creates a new directory ../hotfix-dir checked out to that branch
ls ../hotfix-dir
```

Each worktree is a lightweight checkout that shares the same `.git` object store — no re-cloning needed.

### Create a worktree with a new branch

```bash
git worktree add -b feature/new-work ../new-work main
```

### List active worktrees

```bash
git worktree list
```

### Remove a worktree

```bash
# first, finish your work and delete the branch if needed
git worktree remove ../hotfix-dir

# or just delete the directory and then prune
rm -rf ../hotfix-dir
git worktree prune
```

### Rules

- A branch can only be checked out in **one** worktree at a time
- Each worktree has its own working directory, staging area, and HEAD
- They all share the same repository (objects, refs, config)

### Try it

1. From your repo, create a worktree for a new branch in a sibling directory
2. Make a commit in the new worktree
3. Switch back to your main repo directory — is the commit visible in `git log --all`?
4. List worktrees
5. Remove the worktree when done

---

← [prev](./Lab-7.3-The-Stash.md) | [next](./Lab-7.5-Searching.md) → | 🏠 [home](./README.md)
