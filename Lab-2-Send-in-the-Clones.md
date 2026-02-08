_Cloning_

    git clone https://github.com/WhatIfWeDigDeeper/git-training.git
    cd git-training

    git remote
    git remote -v
    git remote show origin

_Forking [GitHub](https://help.github.com/articles/configuring-a-remote-for-a-fork/)_

    # fork repo in GitHub
    git clone https://github.com/WhatIfWeDigDeeper/git-training.git fork-gtrain-repo
    git remote
    git remote -v
    git remote show origin
    # upstream
    git remote add upstream # source repo's clone url
    git remote -v




### Instructions

1. **Clone this repository**. When would you fork instead of clone?
1. Create a new branch with your name (e.g. `yourname/notes`)
1. Check status
1. Check log
1. Add a notes.md file with some content
1. Stage this file
1. Check status
1. Make another change to notes.md
1. Check status — why does the file appear twice (staged and modified)?

---

← [prev](./The-Commit.md) | [next](./Lab-2.6-Tagging.md) → | 🏠 [home](./README.md)
