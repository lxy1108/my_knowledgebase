# Git Commands Reference

## Basic Commands

### Repository Setup and Configuration

- **`git init`**
  - Initialize a new local git repository
  - Creates a `.git` directory in the current folder

- **`git clone <url>`**
  - Clone an existing remote repository to local machine
  - Creates a complete copy of the repository including all history

- **`git config`**
  - Configure git settings
  - Common usage:
    - `git config --global user.name "Your Name"`
    - `git config --global user.email "your.email@example.com"`
    - `git config --global core.editor "vim"`

### Staging and Committing

- **`git status`**
  - Show the working tree status
  - Displays modified, staged, and untracked files

- **`git add <file>`**
  - Add file contents to the staging area
  - Variations:
    - `git add .` - Add all files in current directory
    - `git add -A` - Add all files (including deletions)
    - `git add -u` - Add only modified/deleted files

- **`git commit -m "message"`**
  - Record changes to the repository
  - Creates a new commit with staged changes
  - Tips: Write clear, descriptive commit messages

- **`git commit -am "message"`**
  - Stage and commit all modified files in one step
  - Does NOT include untracked files

- **`git restore <file>`**
  - Restore working tree files
  - Discard changes in working directory
  - Equivalent to: `git checkout -- <file>`

## Branching and Merging

### Branch Operations

- **`git branch`**
  - List all local branches
  - Current branch is highlighted with `*`

- **`git branch <branch-name>`**
  - Create a new branch
  - Does NOT switch to the new branch

- **`git branch -d <branch-name>`**
  - Delete a branch (must be merged)
  - Use `-D` to force delete unmerged branches

- **`git checkout <branch-name>`** / **`git switch <branch-name>`**
  - Switch to a different branch
  - Updates working directory to the specified branch

- **`git checkout -b <branch-name>`** / **`git switch -c <branch-name>`**
  - Create and switch to a new branch in one command

### Merging and Rebasing

- **`git merge <branch-name>`**
  - Merge changes from another branch into current branch
  - Creates a merge commit if there are divergent histories

- **`git rebase <branch-name>`**
  - Reapply commits on top of another branch
  - Creates linear history, useful for keeping feature branches up-to-date
  - Warning: Do NOT rebase public/shared history

- **`git mergetool`**
  - Visual tool for resolving merge conflicts
  - Uses configured merge tool (vimdiff, opendiff, etc.)

## Remote Operations

### Remote Management

- **`git remote -v`**
  - List all remote repositories with URLs
  - Shows both fetch and push URLs

- **`git remote add <name> <url>`**
  - Add a new remote repository
  - Default remote name is `origin`

- **`git remote remove <name>`**
  - Remove a remote repository

- **`git remote rename <old> <new>`**
  - Rename a remote repository

### Synchronization

- **`git fetch <remote>`**
  - Download objects and refs from remote repository
  - Does NOT merge changes into local branches

- **`git pull <remote> <branch>`**
  - Fetch from and integrate with another repository
  - Equivalent to: `git fetch` + `git merge`

- **`git pull --rebase <remote> <branch>`**
  - Fetch and rebase local changes on top of remote
  - Creates linear history

- **`git push <remote> <branch>`**
  - Update remote refs along with associated objects
  - Upload local commits to remote repository

- **`git push -u <remote> <branch>`**
  - Push and set upstream branch
  - First time pushing a new branch

- **`git push --force`**
  - Force push, overwriting remote history
  - **Warning**: Dangerous, can lose commits
  - Use `--force-with-lease` as safer alternative

## History and Inspection

### Viewing History

- **`git log`**
  - Show commit logs
  - Common options:
    - `git log --oneline` - Compact format
    - `git log --graph` - ASCII graph of branches
    - `git log --all` - All branches
    - `git log -n 10` - Last 10 commits

- **`git show <commit>`**
  - Show commit details with diff
  - Can show commits, tags, or trees

- **`git diff`**
  - Show changes between commits, trees, etc.
  - Common usage:
    - `git diff` - Unstaged changes
    - `git diff --staged` - Staged changes
    - `git diff HEAD` - All changes
    - `git diff <branch1> <branch2>` - Compare branches

### Viewing Specific Changes

- **`git blame <file>`**
  - Show what revision and author modified each line
  - Useful for code review and debugging

- **`git log --follow <file>`**
  - Show history including renames
  - Useful for tracking file movement

- **`git log -p <file>`**
  - Show commit history with patch for specific file

## Undo and Recovery

### Undoing Changes

- **`git reset --soft HEAD~1`**
  - Undo last commit, keep changes staged
  - Useful for modifying the last commit

- **`git reset --mixed HEAD~1`** / **`git reset HEAD~1`**
  - Undo last commit, keep changes unstaged
  - Default reset mode

- **`git reset --hard HEAD~1`**
  - Undo last commit, discard all changes
  - **Dangerous**: Changes are lost

- **`git revert <commit>`**
  - Create new commit that undoes previous commit
  - Safe way to undo public commits

### Recovery

- **`git reflog`**
  - Show reference logs
  - Useful for recovering lost commits
  - Reference log records all branch updates

- **`git checkout <commit>`** / **`git switch --detach <commit>`**
  - Checkout a specific commit
  - Enter detached HEAD state for inspection

- **`git checkout -`** / **`git switch -`**
  - Switch to previous branch

## Stashing

- **`git stash`**
  - Stash local changes away
  - Temporarily saves modifications

- **`git stash list`**
  - List all stashed changes

- **`git stash apply`**
  - Apply most recent stash

- **`git stash pop`**
  - Apply and remove most recent stash

- **`git stash drop`**
  - Remove most recent stash

- **`git stash clear`**
  - Remove all stashed states

## Tagging

- **`git tag`**
  - List all tags

- **`git tag <tag-name>`**
  - Create a lightweight tag

- **`git tag -a <tag-name> -m "message"`**
  - Create an annotated tag with message

- **`git push --tags`**
  - Push all tags to remote

- **`git checkout <tag-name>`**
  - Checkout code at specific tag

## Useful Combinations

### Common Workflows

**Create feature branch and switch:**
```bash
git checkout -b feature-branch
# or
git switch -c feature-branch
```

**Update local branch with remote changes:**
```bash
git pull --rebase origin main
```

**Undo last commit but keep changes:**
```bash
git reset --soft HEAD~1
```

**Modify last commit (add forgotten file):**
```bash
git add forgotten_file.txt
git commit --amend
```

**Interactive rebase (clean up history):**
```bash
git rebase -i HEAD~5
```

**Cherry-pick specific commit:**
```bash
git cherry-pick <commit-hash>
```

### Search Commands

- **`git log --grep="pattern"`**
  - Search commit messages

- **`git log --author="name"`**
  - Search by author

- **`git log --since="2024-01-01" --until="2024-12-31"`**
  - Filter by date range

- **`git grep "pattern"`**
  - Search file contents in repository

## Tips and Best Practices

1. **Commit Often**: Small, focused commits are easier to understand and revert
2. **Write Clear Messages**: Use imperative mood ("Add feature" not "Added feature")
3. **Review Before Pushing**: Use `git status` and `git diff` to verify changes
4. **Use Branches**: Keep main branch stable, develop on feature branches
5. **Pull Before Push**: Always sync with remote before pushing changes
6. **Never Force Push on Shared Branches**: Use `--force-with-lease` instead
7. **Use `.gitignore`**: Exclude temporary files, build artifacts, and sensitive data

---

**Last Updated**: 2026-01-08
**Purpose**: Quick reference for daily git operations
