# Git Features

| **Author** | **Created on** | **Version** | **Last updated by** | **Internal Reviewer** | **Reviewer L0** | **Reviewer L1** | **Reviewer L2** |
|------------|----------------|-------------|----------------------|-----------------------|----------------|----------------|----------------|
| Anuj Yadav | 15-02-2025    | v1.1         | Anuj Yadav  | Komal Jaiswal         |                |                |                |

---

# Table of Contents

1. [Introduction to Git](#1-introduction-to-git)  
2. [Features of Git](#2-features-of-git)  
3. [How Git Works](#3-how-git-works)  
4. [Benefits of Using Git](#4-benefits-of-using-git)  
5. [Comparing Git with Other VCS Tools](#5-comparing-git-with-other-vcs-tools)  
6. [Best Practices for Using Git](#6-best-practices-for-using-git)  
7. [Conclusion](#7-conclusion)  
8. [FAQs](#8-faqs-about-git)  

---

## 1. Introduction to Git

Git is a **distributed version control system** that helps developers track changes in their code, collaborate with teams, and manage project history efficiently.

### Why Use Git?

| **Feature**         | **Description**                                     |
|---------------------|-----------------------------------------------------|
| **Distributed**     | Every developer has a full copy of the repository.  |
| **Fast**           | Local operations are quick, reducing delays.        |
| **Branching**      | Developers can work independently on features.      |
| **Security**       | Uses cryptographic hashing to secure history.       |

---

## 2. Features of Git

| **Feature**            | **Description**                                             |
|------------------------|-------------------------------------------------------------|
| **Branching & Merging** | Create separate branches for new features and merge them. |
| **Distributed VCS**     | Every developer has a local copy of the repository.       |
| **Commit History**      | Tracks every change with commit messages.                 |
| **Collaboration**       | Multiple developers can work on the same project.        |
| **Undo Changes**        | Revert or reset commits if needed.                        |
| **Security**           | Uses SHA-1 hashing for integrity.                         |

---

## 3. How Git Works

| **Concept**       | **Description**                                      |
|------------------|------------------------------------------------------|
| **Repository**   | A folder that contains all version-controlled files. |
| **Commit**       | A snapshot of changes in the repository.             |
| **Branch**       | An independent line of development.                   |
| **Merge**        | Combines changes from different branches.             |
| **Pull**         | Fetches and integrates changes from remote.          |
| **Push**         | Sends local commits to a remote repository.          |

---

## 4. Benefits of Using Git

| **Benefit**          | **Description**                                      |
|----------------------|------------------------------------------------------|
| **Faster Development** | Enables teams to work in parallel.                |
| **Reliable**         | Stores data in a distributed manner.                |
| **Flexible**        | Works with different workflows.                      |
| **Open-Source**     | Free to use and widely supported.                    |
| **Secure**          | Ensures integrity using cryptographic hashing.       |

---

## 5. Comparing Git with Other VCS Tools

| **Feature**           | **Git**                        | **SVN**                       | **Mercurial**                 |
|----------------------|------------------------------|------------------------------|------------------------------|
| **Distributed**      | Yes                           | No                            | Yes                           |
| **Branching**       | Lightweight & fast           | Heavy and slow               | Good branching support       |
| **Speed**           | Very fast                    | Slower due to centralization | Fast                         |
| **Security**        | SHA-1 hashing                | Less secure                  | Secure                        |

---

## 6. Best Practices for Using Git

| **Best Practice**       | **Description**                                     |
|-------------------------|-----------------------------------------------------|
| **Write Clear Commits** | Use meaningful messages for future reference.     |
| **Use Branches**        | Keep `main` or `master` clean, work on feature branches. |
| **Pull Before Push**    | Sync with the remote repo before pushing changes. |
| **Use .gitignore**      | Exclude unnecessary files from version control.   |
| **Review Code**         | Use pull requests for better collaboration.       |

---

## 7. Conclusion

Git is a powerful version control system that enables teams to develop, collaborate, and manage code efficiently. By leveraging Git's features like branching, merging, and distributed workflows, teams can work faster and more securely.

---

## 8. FAQs About Git

**Is Git free to use?**  
Yes, Git is open-source and free for everyone.

**Can Git be used without GitHub?**  
Yes, Git is independent of GitHub. GitHub is just a platform for hosting Git repositories.

**What is the difference between Git and GitHub?**  
Git is a version control system, while GitHub is a hosting service for Git repositories.

**How do I undo changes in Git?**  
You can use `git revert`, `git reset`, or `git checkout` depending on your needs.

**How do I set up Git on my system?**  
Install Git and configure your username and email using:
```
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

## Contact Information

| **Name**       | **Email Address**        |
|----------------|--------------------------|
|Anuj Yadav   | <anuj.yadav@mygurukulam.co> |

---

### References

| Service          | Documentation Link                                                  |
|------------------|---------------------------------------------------------------------|
| **Git**         | [Official Documentation]()                  |
| **Git Guide**   | [Atlassian Git Tutorials]() |
