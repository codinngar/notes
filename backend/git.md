## Setup and Configuration
```bash
# Initialize a new Git repository
git init
# Clone and create a local copy of a remote repository
git clone <url>
# Configure global Git settings
git config --global <setting_name> <value>
# Configure local Git settings for a specific repo
git config --local <setting_name> <value>
# Show a summary of your Git configuration settings
git config --list
# Set a custom text editor for Git messages
git config --global core.editor "<editor_command>"
# Create a Git command alias
git config --global alias.<shortcut> <command>
```

## File Operations
```bash
# Show working tree status
git status
# Add files to the staging area
git add <file(s)>
# Remove files from working tree and staging area
git rm <file(s)>
# Show files in the staging area
git ls-files
# Move or rename a file
git mv <old_file> <new_file>
# Commit changes with a message
git commit -m "commit message"
# Show commit details
git show <commit_id>
# Show differences between working tree and last commit
git diff
# Show differences between two commits
git diff <commit_id1>..<commit_id2>
# Unstage a file, but keep in the working directory
git rm --cached <file_name>
# Restore the last changes from staging area
git restore <file(s)>
# Unstage from staging area
git restore <file(s)> --staged
```

## Branching and Merging
```bash
# List all branches
git branch
# Create a new branch
git branch <branch_name>
# Switch to a specific branch
git switch <branch_name>
# Merge a branch into the current branch
git merge <branch_name>
# Delete a specific branch
git branch -d <branch_name>
# List all remote branches
git branch -r
# Rename current branch
git branch -m <branch_name>
````

## Remote Repositories
```bash
# List remote repositories
git remote
# Show remote repository details
git remote -v
# Add a remote repository
git remote add <name> <url>
# Fetch from a remote repository
git fetch <remote_name>
# Pull changes from a remote branch
git pull <remote_name> <remote_branch>
# Push changes to a remote repository
git push <remote_name> <local_branch>
# Remove a remote repository
git remote rm <remote_name>
# Display information about a specific remote repository
git remote show <remote_name>
# Show the tracking branches for remote repositories
git remote show <remote_name> --verbose
# List all remote branches that have been merged into the current branch
git branch -r --merged
# List all remote branches not yet merged into the current branch
git branch -r --no-merged
```

## Commit History
```bash
# Show commit history
git log
# Display a condensed commit history
git log --oneline
# Show branching commit history
git log --graph
# Filter commit history by author
git log --author=<author_name>
# Show commit history since specific date
git log --since=<date>
# Show commit history until specific date
git log --until=<date>
```

## Tags
```bash
# List all tags
git tag
# Create a new tag at a specific commit
git tag <tag_name> <commit_id>
# Create an annotated tag with a message
git tag -a <tag_name> -m "tag message"
# Delete a specific tag
git tag -d <tag_name>
# Delete a specific remote tag
git push <remote_name> --delete <tag_name>
# Show information about a specific tag
git show <tag_name>
```

## Stashes
```bash
# Temporarily save changes in the working tree
git stash save "stash message"
# List all stashes
git stash list
# Apply changes from a specific stash
git stash apply <stash>
# Remove a specific stash
git stash drop <stash>
# Remove all stashes
git stash clear
```

## Commit Management
```bash
# Modify the latest commit
git commit --amend
# Create a new commit that undoes changes from a previous commit
git revert <commit_id>
# Discard changes and move HEAD to a specific commit
git reset --hard <commit_id>
# Move HEAD to a specific commit, but preserve staged changes
git reset --soft <commit_id>
# Show a record of all changes made to the local repository head
git reflog
```

## Authentication
```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "email@gmail.com"
# Copy file content
cat ~/.ssh/id_ed25519.pub
# Go to github settings and add a new ssh key with the file content
```