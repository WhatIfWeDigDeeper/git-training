[ProGit](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)

Changing the base of the branch, in other words, the parent of the divergent commit is instead set to the latest commit in master.

Merging vs rebasing

type|history|
|:---|:-----|
merge|preserves actual branching
rebase|edit - linear history

Database objects in Git are *immutable*.  If you change anything, then you get a different hash.  When rebasing, Git creates new commits, since they have different parents.  The old commits in the branch are orphaned and only reachable by sha (see git reflog).  Git will garbage collect unreachable objects.


### Warning:  “Do not rebase commits that exist outside your repository.” or "Never rebase shared commits"


    # like a single commit rebase.
    git cherry-pick #sha

---

← [prev](./Lab-3.5-Remote-Branches.md) | [next](./Lab-5.3-Cherry-Picking.md) → | 🏠 [home](./README.md)
