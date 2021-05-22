[7.8 Git Tools - Advanced Merging](https://git-scm.com/book/en/v2/Git-Tools-Advanced-Merging)

> Make sure working directory is clean before starting any merge

Bailing out of a merge conflict.

    git status -sb
    UU README.md

    git merge --abort

> WARNING! Any uncommitted work will be lost

    git reset --hard HEAD

Whitespace

    # ignore whitespace completely
    git merge -Xignore-space-change experiment

    # for each line treat whitespace characters as equivalent
    git merge -Xignore-space-change experiment

### File storage during merge conflict operations

|Stage|Description|
|:------|:----------|
| 1| Common Ancestor
| 2| Your version
| 3| Their version (from MERGE_HEAD)

Output from merge stage to a file

    git show :1:README.md > README.common.md
    git show :2:README.md > README.ours.md
    git show :3:README.md > README.theirs.md

    # can also get sha1s
    git ls-files -u

See what changed after merge and before committing merge
    
    git diff --ours
    git diff --theirs
    git diff --base

    git checkout --conflict=diff3 # shows ours, theirs, and base markers in file
    git checkout --conflict=merge # default

    # choose winning side
    git checkout --ours
    git checkout --theirs

    # show commits involved in merge
    git log --oneline --left-right HEAD...MERGE_HEAD

    # show only commits where there are merge conflicts
    git log --oneline --left-right --merge

    # shows how last merge resolved
    git log --cc -p -1

### Playing favorites

    # merge common, but when conflict, choose side
    git merge -Xours experiment
    
    # individual file merge
    git merge-file --ours

### Un-cherry picking

    git revert #sha1