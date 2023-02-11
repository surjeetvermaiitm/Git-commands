# Git-Assignment

### Getting & Creating Projects

| Command                                                           | Description                                |
| ----------------------------------------------------------------- | ------------------------------------------ |
| `git init`                                                        | Initialize a local Git repository          |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command                            | Description                                       |
| ---------------------------------- | ------------------------------------------------- |
| `git status`                       | Check status                                      |
| `git add [file-name.txt]`          | Add a file to the staging area                    |
| `git add -A`                       | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes                                    |
| `git rm -r [file-name.txt]`        | Remove a file (or folder)                         |

### Branching & Merging

| Command                                              | Description                                             |
| ---------------------------------------------------- | ------------------------------------------------------- |
| `git branch`                                         | List branches (the asterisk denotes the current branch) |
| `git branch -a`                                      | List all branches (local and remote)                    |
| `git branch [branch name]`                           | Create a new branch                                     |
| `git branch -d [branch name]`                        | Delete a branch                                         |
| `git push origin --delete [branch name]`             | Delete a remote branch                                  |
| `git checkout -b [branch name]`                      | Create a new branch and switch to it                    |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it                  |
| `git branch -m [old branch name] [new branch name]`  | Rename a local branch                                   |
| `git checkout [branch name]`                         | Switch to a branch                                      |
| `git checkout -`                                     | Switch to the branch last checked out                   |
| `git checkout -- [file-name.txt]`                    | Discard changes to a file                               |
| `git merge [branch name]`                            | Merge a branch into the active branch                   |
| `git merge [source branch] [target branch]`          | Merge a branch into a target branch                     |
| `git stash`                                          | Stash changes in a dirty working directory              |
| `git stash clear`                                    | Remove all stashed entries                              |

### Sharing & Updating Projects

| Command                                                                           | Description                                                 |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| `git push origin [branch name]`                                                   | Push a branch to your remote repository                     |
| `git push -u origin [branch name]`                                                | Push changes to remote repository (and remember the branch) |
| `git push`                                                                        | Push changes to remote repository (remembered branch)       |
| `git push origin --delete [branch name]`                                          | Delete a remote branch                                      |
| `git pull`                                                                        | Update local repository to the newest commit                |
| `git pull origin [branch name]`                                                   | Pull changes from remote repository                         |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git`     | Add a remote repository                                     |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH                     |

### Inspection & Comparison

| Command                                    | Description                    |
| ------------------------------------------ | ------------------------------ |
| `git log`                                  | View changes                   |
| `git log --summary`                        | View changes (detailed)        |
| `git log --oneline`                        | View changes (briefly)         |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### Important

| Command                                         | Description                                                                   |     |
| ----------------------------------------------- | ----------------------------------------------------------------------------- | --- |
| `git restore --staged name.txt`                 | Unstage                                                                       |     |
| `git log --graph --decorate --oneline`          | git history in tree form                                                      |     |
| `git log`                                       | viw changes                                                                   |     |
| `git reset commit_id`                           | commit abobe mentioned commit will get removed (will go to unstaged area)     |     |
| `git stash`                                     | send staged code/file to back stage area                                      |     |
| `git stash pop `                                | back to staged area                                                           |     |
| `git stash clear`                               | delete file which are on back stage                                           | `   |
| `git remote add origin git_repo_url`            | add remote to local                                                           |     |
| `git remote -v`                                 | fetch and push available option                                               |     |
| `git push origin [branch-name]`                 | push                                                                          |     |
| `https://learngitbranching.js.org/`             | for git branch                                                                |     |
| `git clone personal_account_forked-link`        | clone                                                                         |     |
| `git remote add upstram sforked_source_link`    | add for pull req                                                              |     |
| `git remote -v`                                 | to check for fetch and push option                                            |     |
| `git push origin branch -f`                     | force push after removing any commit                                          |     |
| `git checkout main`-->`git fetch --all --prune` | to fetch all the changes occured in other branch or upstram(source of forked) |     |
| `method2 --> git reset --hard upstream/main`    | to fetch all the changes occured in other branch or upstram(source of forked) |     |
| `git push origin main`                          | push to main                                                                  |     |
| `git pull upstream main`                        | pull from upstream main                                                       |     |
| `git rebase -i commit_id`                       | pick or squash (merge in prev pick)                                           |     |
| `git reset --hard commit_id`                    | commit abobe mentioned commit will get removed (will go to unstaged area)     |     |
| inside feature branch `git rebase main`         | updsatew main commits in main feature                                         |     |
| `git merge feature`                             | fast forward merge(read more about fast forward and recursive merge)          |     |
| chery-pick merge explore                        | explore more                                                                  |     |

Steps

1. Create a new repository in Github

```
used gui for creating repo
```

2. Add a commit to main branch

```
git add .
git commit -m "1st commit to main"
git push origin main
```

3. Create a feature-1 branch from the main

```
git checkout -b feature-1
```

4. Add a commit to feature-1 branch

```
git add .
git commit -m "1st commit to feature-1"
git push origin feature-1
```

5. Add a commit to main branch

```
git checkout main
git pull origin feature-1
git add .
git commit -m "2nd commit to main"
git push origin main
```

6. Create another feature-2 branch from main

```
git branch feature-2
```

7. Add a commit to main branch

```
git add .
git commit -m "3rd commit to main"
git push origin main
```

8. Merge feature-1 to main

```
git merge feature-1
```

9. Add a commit to main branch

```
git add .
git commit -m "4th commit to main"
git push origin main
```

10. Add a commit to feature-2 branch

```
git checkout feature-2
git pull origin main
git add .
git commit -m "1st commit to feature-2"
git push origin feature-2
```

11. Merge feature-2 to main

```
git checkout main
git merge feature-2
git push origin main
```

12. Delete feature-1 and feature-2 branches

```
git branch -d feature-1 feature-2
git push origin --delete feature-1 feature-2
```

13. History Graph

![History Graph](Screenshot%202023-02-10%20at%207.11.32%20PM.png)

unstage

```
git restore --staged name.txt
```
