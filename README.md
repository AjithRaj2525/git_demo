# Experiment 1: Git Repository

## Aim

To demonstrate how to create a project in a remote repository and apply Git concepts such as branching, diff, merging, merge conflict resolution, and pull requests using GitHub.

## Objectives

- Create a remote repository on GitHub.
- Clone the repository to the local system.
- Add, commit, and push files to GitHub.
- Create and switch between branches.
- Compare changes between branches using `git diff`.
- Create and resolve a merge conflict.
- Understand the pull request workflow.

## Software Requirements

- Git
- GitHub account
- Visual Studio Code
- macOS Terminal

## Repository Details

- **Repository name:** `git_demo`
- **Remote URL:** `https://github.com/AjithRaj2525/git_demo.git`
- **Feature branch:** `feature1`
- **Main branch:** `main`
- **Sample file:** `file.txt`

---

## Step 1: Create a Repository on GitHub

1. Open [GitHub](https://github.com/).
2. Click the **+** icon and select **New repository**.
3. Enter the repository name as `git_demo`.
4. Select Public or Private.
5. Leave the README initialization option unchecked.
6. Click **Create repository**.

The remote repository is now ready.

## Step 2: Clone the Repository to the Local System

Open the terminal and navigate to the DevOps directory.

```bash
cd ~/Documents/DevOps
```

Clone the repository into a folder named `git-demo-practice`.

```bash
git clone https://github.com/AjithRaj2525/git_demo.git git-demo-practice
```

Navigate into the cloned repository.

```bash
cd git-demo-practice
```

Check the current repository status.

```bash
git status
```

Check the remote repository URL.

```bash
git remote -v
```

The remote URL should be:

```text
https://github.com/AjithRaj2525/git_demo.git
```

## Step 3: Create a File and Make the Initial Commit

Create a file named `file.txt`.

```bash
touch file.txt
```

Open the file in Visual Studio Code.

```bash
code file.txt
```

Add the following content:

```text
Hello, GitHub
```

Save the file.

### Add the file to the staging area

```bash
git add file.txt
```

### Commit the changes

```bash
git commit -m "Initial commit"
```

### Push the changes to GitHub

```bash
git push origin main
```

Open the GitHub repository and verify that `file.txt` is present with the content `Hello, GitHub`.

## Step 4: Create and Switch to a Feature Branch

Create a new branch named `feature1`.

```bash
git branch feature1
```

Switch to the feature branch.

```bash
git checkout feature1
```

Verify the current branch.

```bash
git branch
```

The output should show `* feature1`, indicating that the feature branch is active.

## Step 5: Modify the File in the Feature Branch

Open the file.

```bash
code file.txt
```

Add a second line so that the content becomes:

```text
Hello, GitHub
Feature branch update
```

Save the file.

Stage the changes.

```bash
git add file.txt
```

Commit the changes.

```bash
git commit -m "Feature branch update"
```

Push the feature branch to GitHub.

```bash
git push origin feature1
```

Verify that the `feature1` branch appears on GitHub and contains the updated file.

## Step 6: Compare Changes Using Git Diff

Use the following command to compare `main` with `feature1`.

```bash
git diff main..feature1
```

This command displays the differences between the two branches.

The output should show the addition of the following line:

```text
+Feature branch update
```

The `+` symbol indicates a line added in the feature branch compared with `main`.

## Step 7: Create a Change in the Main Branch

Switch back to the main branch.

```bash
git checkout main
```

Open the file.

```bash
code file.txt
```

Replace its contents with:

```text
Hello, GitHub
Main branch change
```

Save the file.

Stage and commit the changes.

```bash
git add file.txt
git commit -m "Main branch change"
```

Push the updated main branch.

```bash
git push origin main
```

Now both branches contain different changes to `file.txt`.

## Step 8: Create a Merge Conflict

While on the main branch, execute:

```bash
git merge feature1
```

Git attempts to merge the feature branch into the main branch. Since both branches changed the same part of `file.txt`, Git reports a merge conflict.

The output may resemble:

```text
CONFLICT (content): Merge conflict in file.txt
Automatic merge failed; fix conflicts and then commit the result.
```

Check the repository status.

```bash
git status
```

The file `file.txt` will be listed as having an unresolved conflict.

## Step 9: Resolve the Merge Conflict

Open the conflicting file.

```bash
code file.txt
```

Visual Studio Code displays options such as:

- Accept Current Change
- Accept Incoming Change
- Accept Both Changes
- Compare Changes

Select **Accept Both Changes** to preserve both versions, then verify that the file contains:

```text
Hello, GitHub
Main branch change
Feature branch update
```

Remove any remaining conflict markers:

```text
<<<<<<<
=======
>>>>>>>
```

Save the file.

### Stage the resolved file

```bash
git add file.txt
```

### Commit the resolution

```bash
git commit -m "Merge conflict resolved"
```

### Push the resolved main branch

```bash
git push origin main
```

Verify the final repository status.

```bash
git status
```

The expected output includes:

```text
On branch main
nothing to commit, working tree clean
```

The merge conflict has now been resolved and the result has been pushed to GitHub.

## Step 10: Create a Pull Request on GitHub

A pull request proposes merging changes from one branch into another.

1. Open the `git_demo` repository on GitHub.
2. Select the **Pull requests** tab.
3. Click **New pull request**.
4. Select `main` as the base branch.
5. Select `feature1` as the compare branch.
6. Review the changes.
7. Click **Create pull request**.
8. Enter a title and description, then submit the request.
9. If GitHub reports that the branches are already up to date or there are no changes to merge, use a new commit on `feature1` to demonstrate the pull request process.

**Note:** In this experiment, the feature branch was merged locally into `main` during the merge-conflict exercise. Therefore, the original feature changes may already be included in `main`. A pull request requires changes on the compare branch that are not already included in the base branch.

## Important Git Commands

| Command | Purpose |
|---|---|
| `git clone URL` | Clones a remote repository |
| `git status` | Displays the current repository status |
| `git remote -v` | Displays configured remote URLs |
| `git add file.txt` | Stages a file |
| `git commit -m "message"` | Saves staged changes in a commit |
| `git push origin main` | Pushes the main branch to GitHub |
| `git branch feature1` | Creates a new branch |
| `git checkout feature1` | Switches to a branch |
| `git diff main..feature1` | Compares two branches |
| `git merge feature1` | Merges the feature branch into the current branch |
| `git log --oneline` | Displays a concise commit history |

## Expected Output

- A GitHub repository is created successfully.
- The repository is cloned to the local system.
- A file is added, committed, and pushed.
- A feature branch is created and updated.
- Changes between branches are displayed using `git diff`.
- A merge conflict is generated and resolved.
- The resolved changes are committed and pushed.
- The pull request workflow is demonstrated.

## Result

The Git repository workflow was demonstrated successfully using GitHub and Git. Branching, committing, pushing, comparing changes, merging, resolving merge conflicts, and the pull request process were explored.
