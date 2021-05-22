### Remote Branches

    each object is immutable and has a unique sha, so easy to synchronize with remote branches

    git ls-remote

    # show URL for origin
    git ls-remote --get-url
    git remote set-url origin https://github.com/some_repo/something.git

    git remote -v  # --verbose

    git remote add upstream https://github.com/VolusionDev/volusion-git-training-repo.git

    git remote show
    git remote -v

    git branch --all
    
    git show-ref master

    # a remote branch is a pointer to a commit

    cat .git/config

    git fetch
    git merge origin/master
    # or
    git pull

    git checkout -b feature/add-col
    # make 2 changes
    git push -u feature/add-col origin/feature/add-col

    1.  git checkout master
    2.  git pull
        # see latest commits on branches
    3.  git branch -v   # or git show-ref
        # squash commits from branch into one commit
    4.  git merge --squash feature/add-col
    5.  git commit -m "[bug/feature number] added ..."
    6.  git show-ref master
    7.  git log --oneline --abbrev-commit
    8.  git push
    9.  git show-ref master
    9.  git branch -d feature/add-col
    10. git push origin --delete feature/add-field
    11. cat .git/config
    




