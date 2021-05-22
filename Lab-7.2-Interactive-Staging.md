# Interactive staging

```bash
echo "new line" >> README.md
git add README.md
echo "new line" >> testing.md
git status

git add -i
```

![add -i](diagrams/add-i.png)

## diff

```bash
git diff --cached
```

![add diff](diagrams/add-i-diff.png)

## patch -p

First make multiple edits in a file

```bash
# wd -> staging
git add --patch   # -p

# wd <- staging
git reset -p

# undo working dir
git checkout -p

# stash <- wd
git stash save -p
```