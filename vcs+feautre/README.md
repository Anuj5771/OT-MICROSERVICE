![Uploading image.png…]()

# GitHub Features Documentation

## Table of Contents

1.  [Introduction](#introduction)
2.  [Key Concept](#key-concept)
    - [Repositories](#repositories)
    - [Branches](#branches)
    - [Pull Requests](#pull-requests)
3.  [Issues](#issues)
4.  [GitHub Actions](#github-actions)
5.  [gitignore](#gitignore)
6.  [Collaboration Tools](#collaboration-tools)
7.  [Conclusion](#conclusion)
8.  [Contact Information](#contact-information)
9.  [References](#references)

## Introduction
Welcome to the GitHub Features Documentation! This guide will help you understand how to effectively use GitHub for version control, collaboration, and more.

---

<details>
  <summary><strong>Key Concept</strong></summary>

  ### Repositories:
  A repository (repo) is a storage space for project files and their version history. Repositories can be local or remote:

  - **Local Repository**: Stored on your computer.
  - **Remote Repository**: Hosted on GitHub or similar platforms. Repositories can be public (visible to everyone) or private (restricted access).

  #### Creating a Repository Locally and Pushing to GitHub:
  1. **Create a Local Repository**:
  ```bash
    mkdir ninja
    cd ninja
    git init
```

### 2. Create a README File:

```bash
 echo "# ninja" > README.md
```

### 3. Commit Initial Files:
```bash
git add .
git commit -m "update_files"
```
## Branches
![Uploading image.png…]()

"Branches in Git enable developers to work on different features or fixes in isolation within the same repository. Each branch is essentially a pointer to a specific commit, allowing developers to work on separate tasks without affecting the main codebase."

Main Branch: The default branch where the final, stable version of the code resides.

Feature Branches: Branches are created from the main branch to work on specific features, bug fixes, or tasks without impacting the main codebase.

### Creating and Managing Branches

#### Creating a New Branch

To create a new branch, use the `git branch` command followed by the branch name. You can also switch to the new branch immediately using `git checkout` or `git switch`.
```bash
  git branch <branch-name>
  git checkout -b <branch-name>
```
## Switching Between Branches

To switch between branches, you can use the git checkout or git switch command:
```bash
 git checkout <branch-name>
```
## Deleting Branches

```bash
Delete a branch locally
git branch -d <branch-name>

 Force delete a branch (useful if the branch is not fully merged)
git branch -D <branch-name>

 Delete a branch remotely
git push origin --delete <branch-name>

```

## Pull Requests (PRs)

A **Pull Request (PR)** is a feature that allows developers to notify team members when they have completed a feature or a set of changes and wish to merge those changes into the main branch. The typical process for a pull request involves the following steps:

1. **Creating a Pull Request**: After pushing commits to a branch, the developer creates a PR to summarize the changes made and their purpose.
   
2. **Reviewing the PR**: Team members review the PR, providing feedback, suggesting improvements, or approving the changes.

3. **Merging the PR**: Once the PR is approved, it can be merged into the main branch, integrating the new changes into the main codebase.

Pull requests are a critical part of the collaborative development process, allowing for code reviews, discussions, and quality control before new code is integrated into the main project.
## Issues

GitHub **Issues** are used to track bugs, tasks, feature requests, and other actionable items within a project. They help you organize and manage work, facilitating team communication and collaboration.

### Creating and Managing Issues

You can create and manage issues directly from the "Issues" tab in your repository. Here's how:

#### 1. **Creating a New Issue**
To create a new issue:
- Go to the "Issues" tab of your repository.
- Click on the **New Issue** button.
- Provide a **title** and a **description** for the issue.
- Optionally, you can assign **labels**, **milestones**, or **assignees** to better organize and track the issue.

#### 2. **Assigning Labels and Milestones**
- **Labels** can be used to categorize issues (e.g., bug, enhancement, question).
- **Milestones** help track progress toward specific goals or versions.

#### 3. **Assigning to Team Members**
- You can assign issues to specific team members to ensure accountability and clear ownership.

#### 4. **Closing an Issue**
Once the work related to the issue is complete, you can close the issue by clicking on the **Close Issue** button. Alternatively, the issue will automatically close when a pull request linked to it is merged.

#### 5. **Reopening an Issue**
If you need to reopen a closed issue, simply click the **Reopen Issue** button.
## GitHub Actions
## Key Features

### Feature Overview

| Feature           | Description                                                           |
|-------------------|-----------------------------------------------------------------------|
| **Automation**     | Automate tasks like code testing, building, and deployment.          |
| **Event-Driven**   | Trigger workflows based on various GitHub events (e.g., push, pull request). |
| **Custom Workflows** | Create customized workflows for different environments and processes. |
| **Extensibility**  | Use actions from GitHub’s marketplace or create your own custom actions. |

## .gitignore

The `.gitignore` file is a special file in a Git repository that tells Git which files or directories it should ignore. Files listed in the `.gitignore` file won't be tracked, committed, or pushed to a remote repository. This is commonly used to avoid adding unnecessary or sensitive files to the version control system.

### Why is `.gitignore` Important?

- **Temporary or System Files**: Files generated by your operating system or tools (e.g., logs, cache files, temp files) are not part of your codebase and don't need to be tracked.
- **Configuration Files**: Files that contain local environment configurations (e.g., API keys, passwords) shouldn’t be shared for security reasons.
- **Build Artifacts**: When you compile or build your project, it generates files (like binaries or compiled code) that should not be tracked because they can be recreated from the source code.

### How Does `.gitignore` Work?

1. **Creating a `.gitignore` File**: You can create a `.gitignore` file in the root of your Git repository.
2. **Adding Patterns**: In the `.gitignore` file, you list patterns or file names that you want Git to ignore. These patterns can include specific files, directories, or file types.
3. **Applying the `.gitignore`**: After adding patterns to the `.gitignore` file, Git will stop tracking those files. If the files were already tracked before being added to `.gitignore`, you'll need to manually remove them from the repository using:
   ```bash
   git rm --cached <file>
## Collaboration Tools

GitHub provides several features to enhance collaboration among developers working on the same project.

### 1. **Forking and Cloning**
- **Fork Repositories**: Forking allows you to create your own copy of someone else’s repository to experiment with changes before contributing back.
- **Clone Repositories**: Cloning enables you to create a local copy of a repository, allowing you to work on the project offline and push changes back to GitHub.

### 2. **Branch Protection Rules**
- **Enforce Standards**: Protect your branches by requiring specific checks like code reviews, status checks (CI/CD), or specific approval requirements before merging.
- **Prevent Force Pushes**: Prevent force pushes or deletion of important branches to maintain stability.

---

## Conclusion

GitHub simplifies software development with version control, collaboration, automation, and security features. It helps manage code through repositories, branching, and pull requests, while **GitHub Actions** automates testing and deployment. 

In the OT Microservice project, GitHub is used for efficient code management and collaboration. It supports continuous integration, tracks tasks, and maintains code stability, making it a key tool for project success.
## Contacts

| Name            | Email Address                                         | GitHub Username     | GitHub URL                          |
|-----------------|-------------------------------------------------------|---------------------|-------------------------------------|
| Anuj yadav   | anuj.yadav@mygurukulam.co                |Anuj168        | [Anuj169](https://github.com/Anuj5771/OT-MICROSERVICE/edit/main/vcs%2Bfeautre/README.md#pull-request) |

---

## References

| Links                                                        | Descriptions                                        |
|--------------------------------------------------------------|-----------------------------------------------------|
| [Official GitHub Documentation](https://docs.github.com)      | Official GitHub Documentation                      |
| [Quickstart Guide: Hello World](https://docs.github.com/en/get-started/quickstart/hello-world) | This link provides a quick start guide to GitHub  |
| [GitHub Actions](https://docs.github.com/en/actions)          | GitHub Actions documentation                       |
| [GitHub Enterprise](https://enterprise.github.com)           | Information on GitHub Enterprise                   |
| [GitHub Codespaces](https://github.com/features/codespaces)   | Information on GitHub Codespaces                   |
