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

## Adding Hunks

```bash
git add -p file.txt
# You will be prompted with options to add which hunk to the commit
```

Ref: https://stackoverflow.com/questions/1085162/commit-only-part-of-a-files-changes-in-git

## Cloning

Partial Clone 1
```bash
git clone --filter=blob:none <url>
```
This clone creates a blobless repo. These clones download all reachable commits and trees while fetching blobs on-demand. These clones are best for developers and build environments that span multiple builds.

Partial Clone 2
```bash
git clone --filter=tree:0 <url>
```
This clone creates a treeless clone. These clones download all reachable commits while fetching trees and blobs on-demand. These clones are best for build environments where the repository will be deleted after a single build, but you still need access to commit history.

Shallow Clone
```bash
git clone --depth=1 <url>
```
This clone creates a shallow clone. These clones truncate the commit history to reduce the clone size. This creates some unexpected behavior issues, limiting which Git commands are possible. These clones also put undue stress on later fetches, so they are strongly discouraged for developer use. They are helpful for some build environments where the repository will be deleted after a single build.

Ref: https://github.blog/2020-12-21-get-up-to-speed-with-partial-clone-and-shallow-clone/#:~:text=Git's%20partial%20clone%20feature%20is,your%20repository%20match%20the%20filter.
