# GIT

This repository demonstrates the basic usage of git.

## List Merge Branch

```bash
git branch --merged
git branch --no-merged
git branch -r --merged
```

## Comparing Between Branches

```bash
# Comparing File/Folder
git diff master...feature -- <file>
git difftool master...feature -- <file>

# Comparing Commits between Branches
git log --oneline --graph --decorate --abbrev-commit branch1..branch2

# Comparing All Files between two Branches
git diff branch1..branch2
git difftool branch1..branch2
```
