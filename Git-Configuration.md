## > git config

_Read config settings_

    git config --global --list
    git config --global user.name
    git config --global user.email 
_Write config settings_

    git config --global user.name "Your Name"
    git config --global user.email your.email@gmail.com

    # set default branch name for new repos (Git 2.28+)
    # "master" was the historical default; "main" is now standard
    git config --global init.defaultBranch main

    # default to git status --short
    git config status.short true

    # default pull to rebase
    git config --global pull.rebase true

    # REuse REcorded REsolution
    git config --global rerere.enabled true

    # pager
    git config --global core.pager "diff-so-fancy | less --tabs=4 -RFX"

### [Editor](https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Setup-and-Config)

    # wait flag is important for commit messages.
    # VS Code
    git config --global core.editor "code --wait"

    # or Sublime
    git config --global core.editor "subl -n -w"

    # or vim / nano
    git config --global core.editor vim

    # commit message template (default)
    git config --global commit.template ~/.gitmessage.txt

[Windows](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)    
    
    git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -nosession"

### Diff

[delta](https://github.com/dandavison/delta) — modern diff pager with syntax highlighting and side-by-side view

    git config --global core.pager delta

[diff-so-fancy](https://github.com/so-fancy/diff-so-fancy) — simpler alternative

### Mergetool and Diff Tool

* [Stack Overflow question](https://stackoverflow.com/questions/6412516/configuring-diff-tool-with-gitconfig)
* [git difftool](https://git-scm.com/docs/git-difftool)
* [git mergetool](https://git-scm.com/docs/git-mergetool)

***

## Git ignore

  [.gitignore](https://gist.github.com/subfuzion/db7f57fff2fb6998a16c)

---

← [prev](./Git-install-and-tools.md) | [next](./Chapter-2-Goals.md) → | 🏠 [home](./README.md)
