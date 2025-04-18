---
title: "Git Crash Course for Beginners"
date: 2023-10-31
author: Theo Okafor
description: Git is a widely used version control system that helps you track and manage changes in your software projects. In this crash course, we'll demystify Git for absolute beginners, breaking down the jargon and complexities into simple terms that anyone can understand.
image: https://github.com/DotCampus/dotcampus.github.io/assets/31534129/17f87623-7c9b-45f3-8db0-90514ff66ec3
---

# Git Crash Course for Beginners

## Introduction

In the world of software development, keeping track of changes, collaborating with others, and maintaining the integrity of your code is vital. Imagine working on a complex project with multiple people, making countless changes, and then trying to figure out who did what and when. This is where version control systems, such as Git, come to the rescue.  In this crash course, we'll demystify Git for absolute beginners, breaking down the jargon and complexities into simple terms that anyone can understand.

## What is Git?

**Git** is a widely used version control system that helps you track and manage changes in your software projects. With Git, you can collaborate seamlessly with team members, keep your code organised, and, if needed, turn back time to recover previous versions of your work. Imagine working on a document, and every time you make an edit, you take a snapshot of it. Git does the same for your code. It's your version history.

Git is especially powerful because it's **distributed**. This means that every person working on a project has their own copy of the project's history, not just a single central copy. Think of it like sharing a document with your friends. Each of you has a copy, and you can all make changes. When you're ready, you can bring your changes back together.

## Is Git and GitHub the Same?

No, Git and GitHub are not the same, although they are related.

**Git** is a distributed version control system (DVCS) that is used for tracking changes in source code during software development. Git is a command-line tool that can be used locally on your computer, and it doesn't require a connection to the internet.

**GitHub**, on the other hand, is a web-based platform and service that provides hosting for Git repositories. It's a place where you can store your Git repositories in the cloud. GitHub offers a graphical user interface for managing and collaborating on Git repositories. It also provides additional features such as issue tracking, project management, and wikis.

In summary, Git is the version control system itself, which can be used locally, while **GitHub** is a web-based platform that provides remote hosting and collaboration features for **Git** repositories.

## Key Concepts

### Working Directory, Staging Area, and Repository

Think of your project as a set of documents on your desk. The **working directory** is your desk; it's where you do all your work. When you're satisfied with your work, you pick up the documents you want to save and place them in a special tray on your desk called the **staging area**. Once you've reviewed everything and you're sure you want to keep those changes, you move (**commit**) them to the **repository**, which is like a filing cabinet where you keep all your important documents.

### Commits

A **commit** is like taking a snapshot of your project. It's a record of all the changes you've made at a particular time. Every time you commit, you can add a note explaining what you did. This helps you and your team understand the history of your project.

### Branches

While working on your project, you might want to try out a new idea or work on a particular feature without affecting the main project. Each branch is a unique path that allows you to make changes independently of other branches. Branches are very important for collaboration with different team members on the same project.

### Merging

Like the name implies, merging is how you bring the different *branches* of the project into the main project where the branches originated from. **Merge conflict** when two branches contains changes to the same section of the same file. In this case, the conflict must be manually reviewed by the author(s) and resolved before the conflicting branch can be merged.

## Installation and Setup

Getting started with Git is simple. You just need to download it to your computer, and you're ready to go. Depending on your operating system, installation instructions can vary. Follow the guidelines on the Git website for your specific OS. After installation, you'll want to set up your name and email. This is just so Git knows who you are when you make changes.

## Basic Git Commands

### `git init`

The `git init` command is like saying, "I want this folder to be a git project." When you run it in your project's folder, you're telling Git that this is where you'll be working.

### `git clone`

Cloning a repository is like downloading a copy of a project from a remote server to your local computer. It's how you get your hands on an existing project to work on.

Usage example:

```bash
git clone <repository-URL>
```

### `git add`

This is used to add the work to the staging area, ready for commit.

### `git commit`

Committing is like turning in your work. When you're ready to say, "I'm done with these changes," you commit them. You'll add a note to let yourself (and others) know what these changes are all about.

Usage example:

```bash
git commit -m "adds the login page"
```

### `git status`

When you want to check what's happening with your project, you use `git status`. It's like asking Git, "Hey, what's new?"

### `git log`

With `git log`, you can look back in time and see all your previous snapshots. It's like reading through your project's history.

## Working with Remotes

Working with remote repositories is like having a copy of a project somewhere on the internet. This section covers how you can connect your local project with a remote one.

### `git remote`

Imagine your project lives in two places: your computer and a remote server (like GitHub). The `git remote` command helps you manage these two copies.

### `git fetch` and `git pull`

`git fetch` is like checking if there are any new changes from the remote copy. It doesn't affect your project; it's just looking to see what's new. If you want to actually bring the new changes into your project, you use `git pull`.

### `git push`

When you've made changes locally and you want to share them with the remote project, you use `git push`. It's like saying, "Here are my changes, please update the remote copy."

## Branching and Merging

To follow along with this tutorial, use this [Git Crash Course Repository](https://github.com/TheoOkafor/git-crash-course) template.

- Click “Use this template”
- Select “Create a new repository”
- After creating your repository, clone it to your local using the `git clone` command.

### `git branch`

The main branch is usually named 'master' or 'main'. Use the `git branch` command to list all branches and see which one you're on.

**Example:**

```bash
$ git branch
* main
  feature/login-page
  bugfix/fix-signup-title
```

In this example, the asterisk (*) indicates the current branch (main). You can spot the other branches, like *'feature/login-page'* and *'bugfix/fix-signup-title’.* 

### `git checkout`

The `git checkout` command is used to switch between branches.

**Example:**

```bash
$ git checkout feature/login-page
```

Now you've hopped into the 'feature/login-page' branch. Any changes you make will be part of branch. Try making changes to this branch and committing the change.

### `git merge`

The `git merge` command helps you combine changes from one branch into another.

**Example:**

Suppose you've been working in the 'feature/cool-feature' branch, and now you want to merge these changes into the 'main' branch:

```bash
$ git checkout main
$ git merge feature/login-page
```

This merges the changes from 'feature/login-page' into 'main.' The two branches converge, and your main branch now has the changes from your *login-page* branch.

### `git checkout -b <new-branch-name>`

You can use this command to create a new branch of the current branch and switch to it immediately

```bash
git checkout -b feature/new-feature
```

This is equivalent to running the commands

```bash
git branch feature/new-feature # creates a new branch
git checkout feature/new-feature # switches to the branch
```

## Resolving Conflicts

Conflicts arise when Git can't decide how to merge two versions of a file. For example, you changed a line in a file, and so did someone else on the same file. Git doesn't know which change to keep, and that's where you come in.

Git highlights the conflicting lines, and you decide which change to keep or combine. Here's a simplified version of what a conflict might look like in a file:

```
<<<<<<< HEAD
Your change
=======
Their change
>>>>>>> feature/login-page
```

Your change is the one you made in the current branch (in this case, 'main'), and 'Their change' is from the 'feature/login-page' branch. You need to choose which one to keep or combine them if it makes sense.

## Other Useful Tips

- **Branches** are powerful but can get chaotic without a strategy. It's wise to follow branching conventions like 'feature/', 'bugfix/', or 'hotfix/' before branch names. It keeps things organized and easy to understand.
- **Small Commits**: Frequent, small commits are easier to manage than infrequent, large ones. Smaller commits make it simpler to identify where things went wrong or to cherry-pick specific changes.
- **Small File Changes per Pull Request**: This is related to the above point about small commits. If you are looking for quality reviews from your teammates, keep the file changes per pull request small.
- **Clear and concise commit messages:** Keep your commit messages clear and concise. It should say exactly what your changes are for. Long commit messages often indicates that the commit ought to be more than one.

## Conclusion

You have made it this far. Congratulations! We've journeyed through some vital aspects of Git: basic commands, commits, branching, merging, resolving conflicts, and best practices. These skills are essential for collaborating efficiently and maintaining a well-organised codebase.

Put these into practice and watch yourself turn into a Git pro. What are you waiting for? Start branching, merging, and making a better code history!

## Additional Resources

For further learning, there are many fantastic Git resources available. Here are some helpful links:

- [Pro Git Book](https://git-scm.com/book/en/v2): A comprehensive guide for mastering Git.
- [Atlassian's Git Tutorials](https://www.atlassian.com/git/tutorials): Practical Git tutorials and explanations.
- [GitHub Learning Lab:](https://github.com/apps/github-learning-lab) Interactive Git courses and hands-on projects.

Happy coding!
