# Git Workflow Documentation

## 1. Introduction

Git is a distributed version control system used to track changes in files and collaborate on projects. GitHub hosts Git repositories and supports collaboration through Pull Requests.

## 2. Repository Initialization

```bash
git init -b main
git status
```

These commands initialize a repository with the main branch and display its status.

## 3. Branching Strategy

- `main`: Stable project version.
- `dev`: Integration branch for development changes.
- `feature/documentation`: Branch for a specific feature or documentation update.

Create and switch to a branch:

```bash
git switch -c dev
git switch -c feature/documentation
```

## 4. Staging and Committing

```bash
git add .
git commit -m "Add documentation"
```

Staging selects changes for a commit. A commit records a snapshot of the staged changes.

## 5. Remote Repository

```bash
git remote -v
git push -u origin main
git fetch origin
```

A remote connects the local repository to GitHub. Push uploads commits, while fetch retrieves remote updates.

## 6. Pull Request Workflow

1. Push the feature branch to GitHub.
2. Open a Pull Request from `feature/documentation` to `dev`.
3. Review the changes and merge the Pull Request.
4. Open a Pull Request from `dev` to `main`.
5. Review and merge the changes.

A Pull Request allows changes to be reviewed before merging.

## 7. Merge and Rebase

- `git merge` integrates changes from another branch and may create a merge commit.
- `git rebase` reapplies commits on a new base and rewrites commit history.

Rebase should be used carefully on shared branches.

## 8. Merge Conflict Resolution

1. Inspect the files reported as conflicted.
2. Open each conflicted file.
3. Resolve the conflict markers: `<<<<<<<`, `=======`, and `>>>>>>>`.
4. Review and test the resolved content.
5. Stage the resolved files.
6. Complete the merge commit if required.

## 9. Git Stash

```bash
git stash
git stash list
git stash pop
```

Stash temporarily saves uncommitted changes so you can switch tasks. `stash pop` reapplies the saved changes.

## 10. Git Tags

```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
git tag
git push origin v1.0.0
```

Tags identify specific points in the repository history, commonly for releases.

## 11. Git Ignore

The `.gitignore` file specifies patterns for files that Git should ignore when they are untracked. It helps exclude temporary files, virtual environments, and local secrets.

## 12. Verification

```bash
git status
git branch -a
git log --oneline --graph --all
git tag
```

These commands help verify the working tree, branches, commit history, and tags.