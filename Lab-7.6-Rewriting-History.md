 ### Amending last commit   

    git show HEAD
    git log --oneline --abbrev-commit
    git commit --amend
    git log --oneline --abbrev-commit
    git show HEAD


### Git History Editor
 
    git log --graph --oneline --decorate
    git rebase -i # sha

    # edit history for commits after latest commit to origin/master
    git rebase -i origin/master

    git log --pretty=format:"%h %s" HEAD~3..HEAD
    
    # note sorted in ascending rather than descending
    git rebase -i HEAD~3


Why should you only rebase local commits that have not been shared?


### git revert

Range:

    # revert range of commits from 23589 inclusive to HEAD inclusive.
    git revert 23589a2^..HEAD

Merge Commit:
    
    # choose master to fall back to
    git revert 23539a2 -m 1
    # choose your branch to fall back to
    git revert 23539a2 -m 2

---

← [prev](./Lab-7.5-Searching.md) | [next](./Lab-7.8-Advanced-Merging.md) → | 🏠 [home](./README.md)
