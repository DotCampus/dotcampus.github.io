---
title: "Git Branch Rule: Disabling Commits to Main branch Using Husky"
date: 2023-08-31
author: Theo Okafor
description: Learn how to safeguard your software development project's main branch with Husky and GitHub branch protection rules. Follow our step-by-step guide to integrate Husky's pre-commit checks and configure GitHub's branch protection settings, adding an extra layer of security to your codebase. Elevate your version control strategy and learn how to protect your 'main' branch effectively with this comprehensive approach.
image: https://images.unsplash.com/photo-1556075798-4825dfaaf498?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&w=3600
---

# Git Branch Rule: Disabling Commits to Main branch Using Husky

![Git Branches via Unsplash](https://images.unsplash.com/photo-1556075798-4825dfaaf498?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&w=3600)

<sup>Git Branches by Yancy Min (via Unsplash)</sup>

Version control is the backbone of collaborative software development, and Git reigns supreme in this realm. The main branch, often named 'main' or 'master', represents the stable, production-ready version of your codebase. It  is the heart of your project, and introducing changes directly to it can lead to unintended issues. Imagine if a bug-ridden code snippet finds its way into 'main', impacting your live application. To prevent such mishaps, it's wise to establish a rule that no direct commits should be allowed to the 'main' branch. Instead, all changes should be initiated through feature branches and undergo thorough testing before merging.

> 📢 **Git (Version Control)** is also a part of our programme contents. Visit [**dotcampus.co**](http://dotcampus.co) to register for our **web development**, **frontend** or **backend** engineering programme.

## GitHub Branch Rules:

GitHub offers branch protection rules that adds this layer of security, but you need to be on the paid version to use this. You can configure these rules to enforce code review, status checks, and require specific checks to pass before allowing merges into the 'main' branch.

## **Enter Husky:**

Husky is a pre-commit hook tool that enables you to enforce certain actions before a commit is made. These actions can range from code linting and testing to, in our case, preventing commits to the 'main' branch. If you are not using on paid GitHub organisation, using Husky is the next best safeguard. By integrating Husky into your project, you can create a seamless workflow that ensures only reviewed, high-quality, tested code reaches your main branch.

## **Step-by-Step Implementation of Husky:**

Here's how to set up Husky to disable commits to the 'main' branch:

1. **Install Husky:**
    
    Start by installing Husky as a dev dependency in your project:
    
    ```bash
    npm install husky --save-dev
    ```
    
2. **Configure Husky Hooks:**
    
    Ensure that the script is executable by running:
    
    ```bash
    npm pkg set scripts.prepare="husky install"
    npm run prepare
    ```
    
3. **Add the Script:**
    
    In your project's root directory, locate the `.husky` folder (if it doesn't exist, create it). Inside this folder, add a file named `pre-commit`. This file will contain the script that runs before every commit.
    
    Open the `pre-commit` file and add the following script:
    
    ```bash
    #!/usr/bin/env sh
    . "$(dirname -- "$0")/_/husky.sh"

    branch="$(git symbolic-ref HEAD 2>/dev/null)"

    if [ "$branch" = "refs/heads/main" ]; then
        echo "Commits to the main branch are not allowed. Create a new branch"
        exit 1
    fi

    ```
    
    This script checks if the current branch is 'main'. If it is, the script prevents the commit and displays an error message.
    
4. **Make the Script Executable:**
    
    Ensure that the script is executable by running:
    
    ```bash
    chmod +x .husky/pre-commit
    ```
    
5. **Test Your Setup:**
    
    Create a new branch and try committing to it. Then, attempt to commit directly to the 'main' branch. Husky should prevent the direct commit to 'main'.
    

By setting up Husky with this pre-commit hook, you're adding an extra layer of protection to your main branch, helping maintain code quality and stability. With Husky, you ensure that all changes undergo rigorous testing before they are merged into your production-ready codebase. By enforcing this Git branch rule, you're fostering a safer and more collaborative development environment.

> 📢 **Git (Version Control)** is also a part of our programme contents. Visit [**dotcampus.co**](http://dotcampus.co) to register for our **web development**, **frontend** or **backend** engineering programme.
