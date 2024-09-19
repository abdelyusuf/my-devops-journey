# Git Fundamentals for Visual Learners

Welcome to **Git Fundamentals**! This README will guide you through key concepts in Git, from basic commands to more advanced topics like rebasing and resolving merge conflicts. Designed for visual learners, we'll include diagrams to make these concepts easy to grasp. Let's dive in!

---

## Table of Contents
1. [What is Git?](#what-is-git)
2. [Git Basics](#git-basics)
   - [Commits](#commits)
   - [Branches](#branches)
3. [Collaboration](#collaboration)
   - [Pull Requests](#pull-requests)
   - [Merge Conflicts](#merge-conflicts)
4. [Advanced Git Techniques](#advanced-git-techniques)
   - [Rebasing](#rebasing)
   - [Force Pushing](#force-pushing)
   - [Squashing Commits](#squashing-commits)
5. [Ignoring Files](#ignoring-files)
6. [Helpful Diagrams](#helpful-diagrams)
7. [Credits](#credits)

---

## What is Git?
**Git** is a distributed version control system that helps developers manage code changes, collaborate with teams, and keep track of project history.

---

## Git Basics

### Commits
A **commit** is like a snapshot of your project at a specific point in time. When you commit, you're saving your changes in Git’s history.

- Command: `git commit -m "Message"`
- Diagram:

![Commit Diagram](https://git-scm.com/images/branching-illustration/commits-and-branches.svg)
> Image credit: Git-SCM

### Branches
Branches allow you to work on features or fixes without affecting the main codebase.

- Command: `git branch feature-branch`
- To switch to a branch: `git checkout feature-branch`
- Diagram:

![Branches Diagram](https://git-scm.com/images/branching-illustration/branching-1.svg)
> Image credit: Git-SCM

---

## Collaboration

### Pull Requests
A **Pull Request (PR)** allows you to request changes to be merged into another branch (usually `main` or `develop`). It's essential for team collaboration and code reviews.

1. Create a branch.
2. Make changes.
3. Push to a remote repository.
4. Open a pull request.
   
- Diagram:

![Pull Request Flow](https://guides.github.com/activities/hello-world/pr-split.png)
> Image credit: GitHub Guides

### Merge Conflicts
**Merge Conflicts** occur when two branches modify the same parts of a file, and Git doesn’t know which changes to keep.

To resolve:
1. Open the file and choose which changes to keep.
2. Mark conflict as resolved: `git add <file>`
3. Commit the resolution.

- Diagram:

![Merge Conflict](https://wac-cdn.atlassian.com/dam/jcr:416bb9b0-5f83-43d2-bb77-f2d2ad81b3da/merge-conflict.svg?cdnVersion=710)
> Image credit: Atlassian

---

## Advanced Git Techniques

### Rebasing
**Rebasing** is an alternative to merging that keeps your history clean by reapplying commits on top of another branch.

- Command: `git rebase main`
- Use when you want to keep a linear history without unnecessary merge commits.
- Diagram:

![Rebase vs Merge](https://git-scm.com/images/branching-illustration/rebase.svg)
> Image credit: Git-SCM

### Force Pushing
**Force Push** (`git push --force`) is used when you want to overwrite remote commits, typically after rebasing.

**Warning**: This rewrites history, so use with caution, especially in shared branches.

### Squashing Commits
**Squashing** commits means combining multiple commits into a single one, often done before merging to keep history clean.

- Command: `git rebase -i HEAD~n` (where `n` is the number of commits to squash)
- Diagram:

![Squash Commits](https://raw.githubusercontent.com/commitizen/cz-cli/master/docs/assets/squash-commit-diagram.png)
> Image credit: Commitizen

---

## Ignoring Files
A `.gitignore` file tells Git which files to ignore and not track, preventing unnecessary files (like `node_modules`, build files, or credentials) from being committed.

Example `.gitignore`:

```plaintext
# Ignore node modules
node_modules/

# Ignore logs
*.log

