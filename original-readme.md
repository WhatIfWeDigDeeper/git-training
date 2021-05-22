# git-training

Training course on Git

## setup Git

  a. setup global config
  b. difftool
  c. mergetool
  d. alias
    -- git lol
    -- git rbi rebase -i
    -- git out - ??

## Git overview - Source Control

### git clone

 - git init
 - most likely to do git clone

### git status, add, commit, log, push, diff

// local, staging, commit, push

### branches

## commands

    git checkout
    git checkout -b
    git show HEAD
    git reflog

    # stashing
    git stash
    git stash list
    git stash pop
    git stash branch feature/xxx


    # merging
    git merge // fast-forward, didn't have to merge any changes, just fast forward pointer to commit.

    # rebase
    git rebase
    git rebase -i
    git rbi

    git push origin master :: git push since already tracked.

    # diff
    git diff --cached  // shows differences of staged files

    git reset --hard HEAD

    # merge conflict
    git mergetool
    git status
    git diff --cached
    rm README.md.orig

    git rebase --continue


    #new file
    echo "single > creates a new file" > AdditionalFile.txt

    echo "double >> appends to an existing file" >> README.md

    # branches are labels to particular commits


    # apply a particular commit from another branch on top of master
    git cherry-pick

### Merge Conflicts

can use text editor to resolve differences, will show lines <<<< that are different
git mergetool
