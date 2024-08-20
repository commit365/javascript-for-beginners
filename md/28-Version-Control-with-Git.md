# Lesson 28: Version Control with Git

Version control is an essential part of modern software development, allowing developers to track changes, collaborate on projects, and manage code effectively. Git is one of the most popular version control systems used today. In this lesson, we will introduce Git, cover basic commands, and explain how to track changes and collaborate on projects.

## 1. Introduction to Git

### What is Git?

Git is a distributed version control system that enables multiple developers to work on a project simultaneously without overwriting each other's changes. It allows you to keep a history of changes, revert to previous versions, and manage branches for feature development.

### Key Concepts

- **Repository**: A directory that contains your project files and the entire history of changes made to those files.
- **Commit**: A snapshot of changes made to files in the repository. Each commit has a unique identifier (hash) and a message describing the changes.
- **Branch**: A separate line of development in a repository. You can create branches to work on features or fixes without affecting the main codebase.
- **Merge**: The process of integrating changes from one branch into another.

## 2. Setting Up Git

### Installing Git

To use Git, you need to install it on your computer. You can download Git from the official website: [git-scm.com](https://git-scm.com/).

### Initializing a Repository

Once Git is installed, you can create a new repository or clone an existing one.

#### Creating a New Repository

To create a new Git repository, navigate to your project directory in the terminal and run:

```bash
git init
```

This command initializes a new Git repository in the current directory.

#### Cloning an Existing Repository

To clone an existing repository from a remote source (like GitHub), use the following command:

```bash
git clone <repository-url>
```

Replace `<repository-url>` with the URL of the repository you want to clone.

## 3. Basic Git Commands

### 3.1 Checking the Status

To check the status of your repository and see which files have been modified, added, or deleted, use:

```bash
git status
```

### 3.2 Adding Changes

To stage changes for the next commit, use the `git add` command. You can add individual files or all changes.

- To add a specific file:

```bash
git add <filename>
```

- To add all changes:

```bash
git add .
```

### 3.3 Committing Changes

After staging changes, you can commit them with a descriptive message:

```bash
git commit -m "Your commit message here"
```

### 3.4 Viewing Commit History

To view the commit history of your repository, use:

```bash
git log
```

This command displays a list of commits, including their hashes, authors, dates, and messages.

### 3.5 Creating a Branch

To create a new branch, use the following command:

```bash
git branch <branch-name>
```

### 3.6 Switching Branches

To switch to an existing branch, use:

```bash
git checkout <branch-name>
```

### 3.7 Merging Branches

To merge changes from one branch into another (e.g., merging a feature branch into the main branch), first switch to the target branch and then run:

```bash
git merge <branch-name>
```

### 3.8 Pushing Changes to Remote

To push your commits to a remote repository (e.g., GitHub), use:

```bash
git push origin <branch-name>
```

### 3.9 Pulling Changes from Remote

To fetch and merge changes from a remote repository into your local branch, use:

```bash
git pull origin <branch-name>
```

## 4. Understanding Collaboration with Git

### Working with Remote Repositories

When collaborating on projects, you will often work with remote repositories hosted on platforms like GitHub, GitLab, or Bitbucket. Here’s how to collaborate effectively:

1. **Forking**: If you want to contribute to someone else's project, you can fork the repository to create your own copy. You can then make changes and submit a pull request to the original repository.

2. **Pull Requests**: After making changes in your branch, you can submit a pull request to propose merging your changes into the main repository. This allows the project maintainers to review your changes before integrating them.

3. **Resolving Conflicts**: If multiple people make changes to the same lines of code, a merge conflict may occur. Git will notify you of conflicts, and you will need to manually resolve them before completing the merge.

## Conclusion

In this lesson, you learned about Git and its importance in version control for software development. You explored basic Git commands for tracking changes, managing branches, and collaborating on projects. Understanding Git is essential for working effectively in teams and maintaining a clean history of your code changes. In the next lesson, we will explore more advanced Git features and workflows to enhance your development process!