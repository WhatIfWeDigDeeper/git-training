### The Fourth Area
    
    git stash push
    # or
    git stash

    git stash --u   # include untracked files
    git stash --all
    
    git stash pop

    git stash pop --index   # stage any previously staged files
    
    git stash list

    git stash apply stash@{2}

    git stash drop stash@{2}

    # keeps any staged files
    git stash --keep-index
    
### patch -p
  
    git stash -p

### create a branch out of it

    git stash branch new-branch-name

### clean destruction

    # -n whatIf, dry run
    git clean -d -f -n  # -d remove directories

    # interactive
    git clean -i

---

← [prev](./Lab-7.2-Interactive-Staging.md) | [next](./Lab-7.5-Searching.md) → | 🏠 [home](./README.md)
