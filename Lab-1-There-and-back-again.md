Explore .git

    
    # git count-objects
    # git cat-file -p #sha1


    # no peeking
    git init three && cd three
    git status

    echo "## Three Main Areas of Git" > README.md
    git status
    git add README.md
    git status

    git count-objects
    git log  ## Why?

    echo "1. Working Directory" >> README.md
    git status
    git status --short
    
    git diff
    git add .
    git count-objects
    git reset README.md
    git status
    git add .
    git status
    
    git count-objects  ## Why?
    git commit -m "My 1st Commit"
    git status
    git count-objects  ## Why?
    git log

    echo "2. Staging" >> README.md
    git diff
    git commit -m "My 2nd time"
    git diff
    git diff --staged
    git log

    # amending a commit
    git commit --amend -m "My 2nd commit"
    git log

    git log --patch  # or -p to show the changes introduced in each commit
    git log --stat
    git log -3 --oneline  # show latest 3 commits

    # git log formats
    git log --pretty=oneline
    git log --pretty=short
    git log --pretty=full
    git log --pretty=fuller
    git log --pretty=format:"%h"
    git log --pretty=format:"cm: %h tree: %t parent: %p"
    git log --pretty=format:"cm: %h by %ae"
    git log --pretty=oneline --graph

    # filter commits
    git log --grep WIP --oneline  # show commits containing "WIP" in commit message
    git log -Gcatch --patch  # show commits that added or removed "catch" 

    # summary
    git shortlog --since="2 months ago" --before="1 month ago"
    # no commit messages and show email address
    git shortlog -se

    # history of specific file
    git blame # file name

### Double dot vs Triple dot

https://stackoverflow.com/questions/462974/what-are-the-differences-between-double-dot-and-triple-dot-in-git-com

https://stackoverflow.com/questions/7251477/what-are-the-differences-between-double-dot-and-triple-dot-in-git-dif


### Instructions

1. Create a new local repository called "three" (`git init three && cd three`)
1. Check status — what does it say?
1. Check log — why does it fail?
1. Create a README.md file with some content
1. Check status — what state is the file in?
1. Stage this file
1. Check status — what changed?
1. Check log — why does it still fail?
1. Make another change to README.md
1. Check status — why does the file appear twice?
1. Undo the change to the working directory (hint: `git checkout --` or `git restore`)
1. Check status
1. Unstage the file back to the working directory (hint: `git reset` or `git restore --staged`)
1. Stage the file again
1. Check status
1. Commit the file
1. Check status
1. Check log — what do you see now?

---

← [prev](./Undo.md) | [next](./The-Commit.md) → | 🏠 [home](./README.md)
