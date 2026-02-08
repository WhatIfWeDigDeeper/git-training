What's a branch?

    git branch

    cat .git/refs/heads/master

What's the significance of master?

What is the current branch?

    cat .git/HEAD

What happens when you checkout a branch?

    git checkout master
    cat .git/HEAD
    cat .git/refs/heads/master

Create a new branch

    git branch feature/docs
    git checkout feature/docs

    # or one command
    git checkout -b feature/docs

Show latest commits for each branch

    git branch -v

Show differences between branches

    git diff # source branch # target branch
    git diff master feature/123-add-column # red=not in branch, green=addition from branch
    git diff feature/123-add-column master  # red=not in master, green=addition to branch

Show diff with remote or what you are about to push

    git diff origin/master

Check for whitespace issues

    git diff --check

---

← [prev](./Chapter-3-Goals.md) | [next](./Lab-3.2-Merging.md) → | 🏠 [home](./README.md)
