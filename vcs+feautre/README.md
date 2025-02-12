![image](https://github.com/user-attachments/assets/ba6bb073-02fc-4437-9994-e96c9ec179a9)

| **Author** | **Created on** | **Version** | **Last updated by**|**Internal Reviewer** |**Reviewer L0** |**Reviewer L1** |**Reviewer L2** |
|------------|---------------------------|-------------|---------------------|-------------|-------------|-------------|-------------|
| Anuj yadav|   14-02-2025             | v1.1          | Anuj yadav        |  Komal Jaiswal |  |   |      |

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
![image](https://github.com/user-attachments/assets/a110d80a-9b83-45a5-a0b8-e1b2041f9ac7)

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
### GitHub Security Features

| **Feature**                          | **Description**                                                           | **Commands/Setup**                                           |
|--------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------|
| **Two-Factor Authentication (2FA)**  | Adds an extra layer of security by requiring a second form of verification. | Enable 2FA in GitHub settings under Security & Analysis.    |
| **Secret Scanning**                  | Detects sensitive information (like API keys or passwords) in your code.   | GitHub automatically scans public repositories for secrets.  |
| **Dependabot**                       | Automates security updates for your project dependencies.                  | Enable Dependabot in repository settings.                   |

### Collaborative Development

| **Feature**                          | **Description**                                                           | **Commands/Setup**                                           |
|--------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------|
| **Forking**                          | Create a copy of someone else’s repository to make changes and contribute back. | `git clone <repo-url>` (after forking).                     |
| **Cloning**                          | Download a repository to your local machine to work offline.              | `git clone <repo-url>`                                        |
| **Branch Protection**                | Protects branches by requiring specific checks before merging.           | Set up branch protection in repository settings.            |
| **Code Reviews**                     | Process for reviewing code in pull requests before merging.               | Use the "Review" button in a pull request.                   |


### Automation with GitHub Actions

| **Feature**                          | **Description**                                                           | **Commands/Setup**                                           |
|--------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------|
| **Workflow Triggers**                | Automates tasks based on specific events (e.g., push, pull request).      | Define triggers in `.github/workflows/` YAML files.         |
| **Custom Actions**                   | Create or use pre-built actions to automate workflows.                    | Define actions in workflow YAML or install from GitHub Marketplace. |
| **Example Workflow**                 | Automate testing or deployment using GitHub Actions.                      | See example below for setting up a CI/CD pipeline.           |


# GitHub Features Documentation

## Pull Requests (PRs)

A Pull Request (PR) is a feature that allows developers to notify team members when they have completed a feature or a set of changes and wish to merge those changes into the main branch. Below is the typical process for creating and managing pull requests.

| **Step**                | **Description**                                                                 | **Commands/Actions**                                             |
|-------------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------|
| **1. Creating a Pull Request** | After pushing commits to a branch, a developer creates a PR to summarize the changes made and their purpose. | - Navigate to the GitHub repository. <br> - Click on the "New Pull Request" button. <br> - Select the base and compare branches. <br> - Add a title and description, then click "Create Pull Request". |
| **2. Reviewing the PR** | Team members review the PR, provide feedback, suggest improvements, or approve the changes. | - Comment on specific lines of code using the inline comment feature. <br> - Approve the PR or request changes. |
| **3. Merging the PR**   | Once the PR is reviewed and approved, it can be merged into the main branch, integrating the new changes into the main codebase. | - Click the "Merge" button to merge the PR into the base branch. <br> - Alternatively, use `git merge <branch-name>` in the command line after fetching and checking out the main branch. |

---

## Key Benefits of Pull Requests

| **Feature**                      | **Description**                                                           |
|-----------------------------------|---------------------------------------------------------------------------|
| **Code Reviews**                  | Pull requests allow for peer reviews of changes before they are merged.  |
| **Discussions**                   | Team members can discuss specific code changes and suggest improvements. |
| **Quality Control**               | Ensures that changes meet project standards before integration.          |
| **Track Changes**                 | Pull requests keep a detailed record of what changes were made and why.  |
| **Integration Testing**           | Pull requests can trigger automated tests to ensure changes don’t break the project. |

---

### Conclusion

Pull requests are an essential feature of collaborative development. They help maintain code quality, encourage discussions, and ensure that changes are thoroughly reviewed before being merged into the main branch. 


# GitHub Features Documentation

## Issues

GitHub **Issues** are used to track bugs, tasks, feature requests, and other actionable items within a project. They help you organize and manage work, facilitating team communication and collaboration.

### Creating and Managing Issues

| **Step**                           | **Description**                                                                 | **Actions**                                                       |
|------------------------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------|
| **1. Creating a New Issue**        | To create a new issue:                                                           | - Go to the "Issues" tab of your repository. <br> - Click on "New Issue". <br> - Add a **title** and **description**. <br> - Optionally, assign **labels**, **milestones**, or **assignees**. |
| **2. Assigning Labels and Milestones** | Use labels to categorize issues (e.g., bug, enhancement) and milestones to track progress. | - In the issue, click "Labels" to add tags like bug or enhancement. <br> - Assign a milestone for progress tracking. |
| **3. Assigning to Team Members**   | Assign issues to specific team members to ensure clear ownership and accountability. | - Use the **Assignees** dropdown to select responsible team members. |
| **4. Closing an Issue**            | Once the issue's work is complete, you can close it manually, or it will close automatically when the linked PR is merged. | - Click "Close Issue" to mark the issue as resolved. <br> - The issue closes automatically when a linked PR is merged. |
| **5. Reopening an Issue**          | If the issue needs further attention, reopen it by clicking the "Reopen Issue" button. | - Click on **Reopen Issue** to bring it back into the active list. |

---

## GitHub Actions

GitHub Actions automate tasks like testing, building, and deploying code based on events in the GitHub repository.

### Key Features

| **Feature**                          | **Description**                                                           | **Commands/Setup**                                           |
|--------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------|
| **Automation**                       | Automate tasks such as code testing, building, and deployment.            | Define automation workflows in `.github/workflows/`.        |
| **Event-Driven**                     | Trigger workflows based on specific GitHub events like push, pull request, etc. | Specify events in the YAML file (e.g., `on: push`).         |
| **Custom Workflows**                 | Create customized workflows for different environments or processes.      | Add a custom workflow in the `.github/workflows/` directory. |
| **Extensibility**                    | Use pre-built actions from GitHub Marketplace or create your own.         | Use `uses: actions/checkout@v2` or define custom actions.    |

# GitHub Features Documentation

## .gitignore

The `.gitignore` file is a special file in a Git repository that tells Git which files or directories it should ignore. Files listed in the `.gitignore` file won't be tracked, committed, or pushed to a remote repository.

### Why is `.gitignore` Important?

| **Reason**                         | **Description**                                                             |
|------------------------------------|-----------------------------------------------------------------------------|
| **Temporary or System Files**      | Files generated by the operating system (logs, cache, temp files) don't need to be tracked. |
| **Configuration Files**            | Local environment files (e.g., API keys, passwords) should not be shared for security reasons. |
| **Build Artifacts**                | Files like binaries or compiled code that can be recreated from the source code should not be tracked. |

---

### How Does `.gitignore` Work?

| **Step**                            | **Description**                                                                                  | **Commands/Actions**                                           |
|-------------------------------------|--------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
| **1. Creating a `.gitignore` File** | You can create a `.gitignore` file in the root of your Git repository.                           | - Use `touch .gitignore` to create the file in the root directory. |
| **2. Adding Patterns**              | In the `.gitignore` file, list patterns or file names that you want Git to ignore.                | - Add patterns like `*.log`, `*.tmp`, or `/node_modules/`.       |
| **3. Applying the `.gitignore`**    | After adding patterns, Git will stop tracking those files. If already tracked, manually remove them. | - Run `git rm --cached <file>` to remove previously tracked files. |

---

## Collaboration Tools

GitHub provides several features to enhance collaboration among developers working on the same project.

| **Feature**                          | **Description**                                                          | **Commands/Actions**                                          |
|--------------------------------------|--------------------------------------------------------------------------|--------------------------------------------------------------|
| **1. Forking and Cloning**           | Forking allows you to create your own copy of someone else’s repository to experiment with changes. Cloning enables a local copy for offline work. | - To fork a repo: Click "Fork" on the repository page. <br> - To clone a repo: `git clone <repo-url>` |
| **2. Branch Protection Rules**      | Protect your branches by enforcing standards such as code reviews or status checks (CI/CD) before merging. Prevent force pushes or deletion of important branches. | - Set branch protection in the repository settings. <br> - Enable required checks and reviews before merging. |

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
