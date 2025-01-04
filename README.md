## Removing Branches Locally and Remotely

### **Remove a Branch Locally**
- To delete a branch from your local repository:
  ``write the following command in terminal
  git branch -d <branch_name>

### **Remove a Branch Remotely**
- To delete a branch from the remote repository:
  ``write the following command in terminal
git push origin --delete <branch_name>

----------------------------------------------------

## Annotated Tags vs Lightweight Tags

Git provides two types of tags: **Annotated Tags** and **Lightweight Tags**. Here’s a detailed comparison:

### **1. Annotated Tags**
- **Description**: Annotated tags store metadata such as the tagger's name, email, date, and a message. They are full Git objects.
- **Use Case**: Recommended for marking releases or important milestones in a project.
- **Features**:
  - Contains a message, just like a commit.
  - Can be signed with a GPG key for verification.
  - Stores additional information about the tagger.
- **Commands**:
  - Create an annotated tag:
    ```bash
    git tag -a <tag_name> -m "Tag message"
    ```
  - Example:
    ```bash
    git tag -a v1.0 -m "First release"
    ```
  - Push an annotated tag to the remote:
    ```bash
    git push origin <tag_name>
    ```

---

### **2. Lightweight Tags**
- **Description**: Lightweight tags are simple pointers to a specific commit. They do not store additional metadata or messages.
- **Use Case**: Useful for quick, temporary tags or internal purposes.
- **Features**:
  - Acts like a branch that doesn’t move but lacks metadata.
  - No tagger information or message.
- **Commands**:
  - Create a lightweight tag:
    ```bash
    git tag <tag_name>
    ```
  - Example:
    ```bash
    git tag v1.0
    ```
  - Push a lightweight tag to the remote:
    ```bash
    git push origin <tag_name>
    ```

## Working with Git Tags

### **1. How to List Tags**
To view all the tags in your repository, use the following command:
```bash
git tag

### **1. How to delete Tags**
####Delete a Tag Locally:
To remove a tag from your local repository:
bash
git tag -d <tag_name>

####delete the tag from Remotely:
bash
git push origin --delete <tag_name>


---------------------------------------------------

## When to Use Git Rebase

### **What is Rebase?**
Rebasing in Git is a process of moving or combining a sequence of commits to a new base commit. It helps maintain a cleaner and more linear commit history by avoiding unnecessary merge commits.

---

### **Reasons to Use Rebase**

#### **1. Keep a Linear Commit History**
- Rebase is ideal for keeping your commit history clean and linear, especially in large projects.
- Instead of having multiple merge commits cluttering the history, rebasing re-applies commits directly on top of the base branch.

#### **2. Update a Feature Branch**
- Use rebase to update your feature branch with the latest changes from the `main` branch without creating a merge commit.
- Example:
  ```bash
  git checkout feature-branch
  git rebase main

#### **3. Squash Commits**
- Combine multiple small commits into a single commit for better clarity.
- This is especially useful for cleaning up work-in-progress commits before sharing your branch.
- Example:
  ```bash
  git rebase -i <base_commit>
