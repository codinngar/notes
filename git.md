# Git Course

## Git Configuration

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --global core.editor "nvim"
```

**`git config --global`** stores settings in **`~/.gitconfig`** and affects only the current user

**`git config --system`** stores settings in **`/etc/gitconfig`** and affects all users on the system

**`core.editor`** option is used to set the program that is used to write commit messages

```bash
git config --list # Show current configuration
```

## Git Initialization

```bash
git init # Turn current directory into a repo and add .git folder
```

## Git Commands

```bash
git status # Show files status in the repo
git status -s # Summarize status
```

```bash
git ls-files # Show files in the index (stagging area)
```

```bash
find .git/objects/ -type f # Show files in the repo
```

```bash
git add <FILE> # Add files to the index and start tracking them
```

```bash
git commit -m "MESSAGE" # Commit files from index to the repo to make a new version with a description
```

```bash
git log <OPTIONS> <FILE> # Show git commit history
# <OPTIONS>
# --oneline : show every commit in one line
# --graph : format output in a graph view
# --decoration : decorate output
# --all : show commits in local and remote
# -(number) : show a specific number of commits
```

```bash
git diff <FILE> # Show the difference between the modified and stagged file
git diff <FILE> --staged # Show the difference between the file in the index and repo
git diff <OLD-SHA>..<NEW-SHA> # Show the difference between two commits
```

```bash
git show <SHA> # Show commit changes for a specific commit
```

```bash
git mv <FILE> <DIR> # Move files in the repo instead of usual mv command
```

```bash
git rm --cached <FILE> # Remove files from index
```

```bash
git restore <FILE> # Restore the last changes of files from index
```

```bash
git restore <FILE> --staged # Unstage file
```

```bash
git commit --amend # Edit last commit message
```

```bash
gir reset <OPTIONS> HEAD~(number) # Go back to previous commit
gir reset <OPTIONS> HEAD@{(number)} # Go forward to next commit
# <OPTIONS>
# --hard : change working tree directly to previous version
```

```bash2
git tag -a <VERSION-NAME> -m "MESSAGE" # Add version tag to the last commit
```

## Git Branching

```bash
git branch # List all branched and the green one is the current branch and star means HEAD
```

```bash
git branch <NAME> # Make a new branch
```

```bash
git switch <BRANCH> # Switch to branch
```

```bash
git merge <BRANCH> # Merge given branch with the current branch
```

```bash
git branch --merged # Show merged branchs with the master
```

```bash
git branch -d <BRANCH> # Delete branch
```

```bash
git branch -M <NAME> # Rename current branch
```

## Git Remote

```bash
git clone <URL or PATH> <NEW-NAME> # Clone remote repo and optionally rename it
```

```bash
git remote add <URL> # Add remote to your current local repo
```

```bash
git remote # If the output is origin that means this is a clone from a remote repo
```

```bash
git remote -v # Show remote repo details
```

```bash
git fetch <REMOTE> # Fetch updates from the remote repo to the local remote without merging and if you want to merge it with the local repo run git merge
```

```bash
git pull <REMOTE> # shortcut of fetch and merge
```

```bash
git push <REMOTE> <BRANCH> # Push your local remote to the repo in master branch and if the branch you specify is not exist in the repo you should add option -u to add it to the repo
```

## Github Authentication

```bash
ssh-keygen -t ed25519 -C "your_email@example.com" # Accecpt defaults and passphrase isn't necessary
# then copy ~/.ssh/id_ed25519.pub file contents
# go to github settings and add a new ssh key with the file content
```

## Contribution

To contribute to a github repo first you fork a copy from it to your account and then clone it to you local machine to add edits then push them and then you make a pull request and the repo author has the options to confirm your edits or refuse it

## Abbreviations

- (U) Untracked
- (M) Modified
    - (red color) the modifications not exist in the index or the repo
    - (green color) the modifications exist in the index but not in the repo
