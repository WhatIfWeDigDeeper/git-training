    echo "new line" >> README.md
    git add README.md
    echo "new line" >> testing.md
    git status
    
    git add -i

![add -i](https://github.com/VolusionDev/volusion-git-training-repo/blob/master/diagrams/add-i.png)

6: diff

    git diff --cached

![add diff](https://github.com/VolusionDev/volusion-git-training-repo/blob/master/diagrams/add-i-diff.png)

### patch -p

First make multiple edits in a file

    # wd -> staging
    git add --patch   # -p

    # wd <- staging
    git reset -p

    # undo working dir
    git checkout -p

    # stash <- wd
    git stash save -p