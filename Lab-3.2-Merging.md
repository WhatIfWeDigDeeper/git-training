What's the difference between
* Fast-forward merge
* Merge commit/recursive merge.


Checkout target and then merge from source branch into target.

    feature/add-field> git checkout master
    master> git merge feature/add-field

![log graph](https://github.com/VolusionDev/volusion-git-training-repo/blob/master/diagrams/log-graph.png)

    git log --oneline --decorate --graph --all

Show latest commits for each branch

    git branch -v

### Merge Conflicts

    $ git merge feature/add-field
    Auto-merging index.html
    CONFLICT (content): Merge conflict in index.html
    Automatic merge failed; fix conflicts and then commit the result.


    # tell Git conflict has been resolved.
    git add #filename
    git commit

Make sure your [editor is configured to wait](Git-Configuration)

### Cleanup

    git branch --merged
    git branch --no-merged

    git branch -d feature/add-field
