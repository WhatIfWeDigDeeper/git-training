# Git Quiz — Answer Key

1. **What is contained in a commit?**

   A commit contains a snapshot of the staged files, a pointer to the parent commit(s), the author name and email, the committer name and email, a date/timestamp, and a commit message. Internally, Git stores a commit object that points to a tree object (which represents the directory structure and file contents via blob objects).

1. **What are the 3 areas in Git?**

   - [x] Staged (also called the Index or Staging Area)
   - [ ] It's Complicated
   - [ ] Untracked
   - [x] Repo or History
   - [ ] Backstage
   - [ ] Frozen
   - [x] Working Directory

1. **What commands or actions move a file to different Areas of a repository?**

   - `git add <file>` — moves changes from the Working Directory to the Staging Area
   - `git commit` — moves staged changes from the Staging Area into the Repository (History)
   - `git restore --staged <file>` (or `git reset <file>`) — unstages a file, moving it back from the Staging Area to the Working Directory
   - `git checkout -- <file>` (or `git restore <file>`) — discards working directory changes by replacing them with the version from the Staging Area/Repo

1. **Can a file be staged and modified at the same time? How?**

   Yes. If you stage a file with `git add` and then edit it again, the file will have one version in the Staging Area (the version you added) and a different version in the Working Directory (with your new edits). Running `git status` will show the file in both the "Changes to be committed" and "Changes not staged for commit" sections.

1. **What is the difference between fork and clone?**

   A **fork** is a server-side copy of a repository into your own account (e.g., on GitHub). It creates an independent copy on the remote that you own and can push to. A **clone** is a local copy of a repository downloaded to your machine using `git clone`. You typically fork a repo you don't have push access to, then clone your fork locally.

1. **What are some common log output modifiers and what do they do?**

   - `--oneline` — condenses each commit to a single line (short SHA + message)
   - `--graph` — draws an ASCII graph of the branch/merge history
   - `--all` — shows commits from all branches, not just the current one
   - `--decorate` — shows branch and tag names next to commits
   - `-n <number>` — limits output to the last n commits
   - `--stat` — shows file change statistics (insertions/deletions) per commit
   - `-p` or `--patch` — shows the full diff introduced by each commit
   - `--author=<name>` — filters commits by author
   - `--since` / `--until` — filters commits by date

1. **How would you list all merged branches in a git repo?**

   - [ ] `git branch -m`
   - [ ] `git branch --not-not-merged`
   - [ ] `git branch --no-merged`
   - [x] `git branch --merged`

1. **Can you delete an unmerged branch?**

   - [ ] Yes
   - [ ] No
   - [x] Yes but you have to use -D

   `git branch -d` will refuse to delete an unmerged branch. You must use `git branch -D` (uppercase) to force-delete it.

1. **What is HEAD?**

   HEAD is a pointer to the current commit (or more precisely, to the current branch reference, which in turn points to a commit). It represents "where you are right now" in the repository. When you make a new commit, HEAD advances to that new commit. A "detached HEAD" state occurs when HEAD points directly to a commit instead of a branch.

1. **Given a stash with 3 items how would you apply the 2nd item in the stash to your repo?**

   - [ ] `git stash apply the second one`
   - [ ] `git stash pop pop`
   - [ ] `git stash drop pop`
   - [x] `git stash apply stash@{1}`

   Stash items are zero-indexed, so the 2nd item is `stash@{1}`.

1. **What tag data is added with an annotated tag?**

   - [x] Tag message
   - [x] Tagger
   - [ ] Tag Committer
   - [x] Tag Date
   - [ ] Tag count
   - [ ] Tag Parent

   An annotated tag (created with `git tag -a`) stores the tagger name/email, the date, and a tag message. It is stored as a full object in the Git database, unlike a lightweight tag.

1. **How would you get a count per file of the phrase 'lodash' in a repo?**

   ```
   git grep -c 'lodash'
   ```

   The `-c` flag tells `git grep` to output the count of matches per file rather than showing each matching line.

1. **How would you amend the most recent commit?**

   ```
   git commit --amend
   ```

   This replaces the most recent commit with a new commit that includes whatever is currently staged. It also lets you edit the commit message.

1. **Why should you only rebase local commits that have not been shared?**

   Rebasing rewrites commit history by creating new commits with new SHAs. If other developers have already based work on the original commits, rewriting those commits creates divergent histories. This forces others to reconcile the duplicate changes, leading to messy merges and potential lost work. The golden rule: **do not rebase commits that exist outside your local repository**.

1. **How would you start an interactive rebase?**

   ```
   git rebase -i <base-commit>
   ```

   For example, `git rebase -i HEAD~3` to interactively rebase the last 3 commits, or `git rebase -i main` to rebase onto main.

1. **What are some different modifiers in an interactive rebase?**

   - **pick** — use the commit as-is
   - **reword** — use the commit but edit the commit message
   - **edit** — pause at this commit so you can amend it
   - **squash** — meld this commit into the previous one and combine messages
   - **fixup** — meld this commit into the previous one but discard this commit's message
   - **drop** — remove the commit entirely

1. **Explain the difference between a recursive merge and a fast-forward merge?**

   A **fast-forward merge** happens when the current branch has no new commits since the branch being merged diverged. Git simply moves the branch pointer forward to the latest commit — no new merge commit is created.

   A **recursive merge** (or three-way merge) happens when both branches have diverged with new commits. Git finds the common ancestor, compares both sets of changes, and creates a new **merge commit** with two parents that combines the work from both branches.

1. **What happens if you run the command `git reset --hard HEAD`?**

   It resets both the Staging Area and the Working Directory to match the current commit (HEAD). Any uncommitted changes — both staged and unstaged — are discarded. The commit history itself is unchanged since you're resetting to the commit you're already on.

1. **Command to compare your local changes or differences before pushing your commit(s) to main on the remote**

   ```
   git diff origin/main
   ```

   Or more specifically to compare just the commits:
   ```
   git log origin/main..HEAD
   ```

1. **Command to log or show commits in a branch feature1 that are not in the main branch**

   ```
   git log main..feature1
   ```

1. **Command to log or show unique commits in both branch feature1 and the main branch**

   ```
   git log main...feature1
   ```

   The triple-dot syntax shows commits that are reachable from either branch but not from both. Adding `--left-right` will indicate which side each commit comes from.

1. **Command to clean up or delete a merged local branch named feature1**

   ```
   git branch -d feature1
   ```

1. **Check areas that would be affected by the following commands**

   | Command     |  Working Directory  | Staging |
   | :---------- |     :---:     | :---: |
   | `git reset file1.txt` |    | [x] |
   | `git reset --hard` | [x]  | [x] |
   | `git checkout -- file1.txt` | [x]   |  |
   | `git restore file1.txt` | [x]   |  |
   | `git restore --staged file1.txt` |   | [x] |

24. **What is the difference between `git checkout`, `git switch`, and `git restore`?**

    `git checkout` is a multi-purpose command that can both switch branches and restore files. Because it does two very different things, Git introduced two focused replacements:

    - **`git switch`** — dedicated to switching branches (e.g., `git switch feature1`, `git switch -c new-branch`). It only handles branch operations and is safer because it won't accidentally overwrite files.
    - **`git restore`** — dedicated to restoring file contents (e.g., `git restore file.txt` to discard working directory changes, `git restore --staged file.txt` to unstage). It only handles file restoration.

    Together, `git switch` and `git restore` split the responsibilities of `git checkout` into two clearer, more intentional commands.
