> **Note:** Git's default branch was historically called `master`. Since Git 2.28 (2020), the default is configurable and most new repos use `main`. These examples use `main` — substitute your repo's default branch name if different.

What's a branch?

    git branch

    cat .git/refs/heads/main

What is the current branch?

    cat .git/HEAD

What happens when you checkout a branch?

    git checkout main
    # modern alternative (Git 2.23+):
    git switch main

    cat .git/HEAD
    cat .git/refs/heads/main

Create a new branch

    git branch feature/docs
    git checkout feature/docs

    # or one command
    git checkout -b feature/docs
    # modern alternative (Git 2.23+):
    git switch -c feature/docs

Show latest commits for each branch

    git branch -v

Show differences between branches

    git diff # source branch # target branch
    git diff main feature/123-add-column # red=not in branch, green=addition from branch
    git diff feature/123-add-column main  # red=not in main, green=addition to branch

Show diff with remote or what you are about to push

    git diff origin/main

Check for whitespace issues

    git diff --check

---

← [prev](./Chapter-3-Goals.md) | [next](./Lab-3.2-Merging.md) → | 🏠 [home](./README.md)
