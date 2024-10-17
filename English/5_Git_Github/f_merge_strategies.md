# Merge Strategies in Git

When working with Git, one of the key mechanisms for combining different branches is **merge**. Git allows us to choose different merge strategies using the `-s` option in the `git merge` and `git pull` commands. Some strategies also have their own options, which can be passed using the `-X` argument.

To better understand how these strategies work, imagine you are organizing a party with your friends, and each one brings their own ideas. Some ideas overlap, while others don’t, but in the end, everyone needs to decide together how the party will be. Merge strategies are the rules they follow to combine those ideas into a single plan.

## Ort Strategy (default)
The `ort` strategy is like the main organizer of the party who, in the event of a conflict, ensures that everyone's ideas are fairly considered. It uses a method called the "three-way merge" algorithm that reviews both common ideas (ancestors) and current proposals, trying to combine the best from both.

### Analyzing a Conflict with Ort:
- **Ours Option**: If there's a conflict, our idea is chosen over the others. It’s like saying, "Let’s stick with what I proposed."
- **Theirs Option**: The opposite of `ours`. In case of conflict, the other person's idea is selected.
- **Ignore Whitespace Changes**: Options like `ignore-space-change` and `ignore-all-space` make minor changes, such as whitespace, not generate conflicts. It’s like deciding that it doesn’t matter if someone brings food on paper plates or porcelain, as long as it’s the same food.

### Practical Example:
Imagine two friends suggest how to decorate the room. One suggests red balloons, while the other suggests blue balloons. Using the `ort` strategy, you review the proposals, consult how it was done in previous parties (common ancestors), and decide on a combination that uses both colors.

## Recursive Strategy (previous default)
Before `ort` became the default, the strategy used was `recursive`. It follows a similar "three-way merge" process but differs in how it handles renamed files and minor changes.

### Additional Options for the Recursive Strategy:
- **Patience**: It’s like the party organizer being more patient when combining ideas, allowing more time for each detail to be resolved correctly.
- **No Renames**: This disables rename detection. Useful when you don’t want to complicate things if someone decides to change a file name (or the theme of an activity at the party).

## Other Merge Strategies
Git also has other merge strategies that you can use in specific situations:

- **Resolve**: Useful when you only have two proposals. It attempts to resolve conflicts as best as possible but isn’t good at handling renames.
- **Octopus**: Ideal when you have multiple branches (or proposals) and want to combine them simply, without allowing major conflicts.
- **Ours**: Completely ignores the other ideas and proceeds only with yours. It’s like saying, "This party will be exactly how I want, regardless of everyone else's suggestions."
- **Subtree**: This strategy is like adjusting an idea to fit into the overall context. If someone proposes an activity that is part of a larger one, you first adjust that smaller part to integrate with the whole.

---

### Summary:
Merge strategies in Git are like different ways of making decisions when organizing a group party. Some strategies try to combine the best ideas from everyone, while others favor one idea over another. Knowing which strategy to use depends on how we want to handle conflicts and the different versions of our code.

---

# Git Fast-Forward vs Non-Fast-Forward

**07-03-2023**  
**Blog**  
**8 minutes read (About 1210 words)**  
**Visits**

## Introduction

When we run `git push`, we might encounter rejections because the remote origin branch cannot be fast-forward updated. This happens when we’re not synchronizing properly, and Git prevents the loss of commits. Let's explore the differences between fast-forward and non-fast-forward updates, along with the proper use of `git push --force`.

## Fast-Forward

### What is Fast-Forward?

Imagine you're building a tower with blocks (commits). If you add more blocks on top of an existing structure without removing any blocks below, that’s a fast-forward update. In Git, a fast-forward update occurs when you change a branch from commit A to commit B, where B is a descendant of A. No history is lost in this process.

### Example 1: Basic Fast-Forward

In our first example, you create a local branch and add a commit. Now you want to update the origin branch.

```
     B local branch
    /
---A origin branch
```

After the fast-forward update, the structure looks like this:

```
---A---B origin branch and local branch
```

### Example 2: Multiple Commits

Let’s extend this scenario. You created several commits on your local branch.

```
     B---C local branch
    /
---A origin branch
```

Now, after a fast-forward update, it becomes:

```
---A---B---C origin branch and local branch
```

This is common when you're the sole contributor to a branch.

### Example 3: Updates from Others

What if you were working on a local branch while others updated the origin branch? 

```
     B local branch
    /
---X---A origin branch
```

To sync, you’ll need to pull changes from the origin branch, resulting in a new commit C:

```
     B---C local branch
    /   /
---X---A origin branch
```

Now you can fast-forward update the origin branch, and it will look like this:

```
---X---A---C origin branch and local branch
```

## Non-Fast-Forward

### What is Non-Fast-Forward?

Now, let’s look at a non-fast-forward update. Imagine you and a friend start building two separate towers from the same block (commit X). You add blocks to create commit B, while your friend builds to commit A. If you try to merge these, it’s like trying to stack two unrelated towers on top of each other—Git doesn’t allow that without proper reconciliation.

### Git Rebase Example

In collaborative projects, it’s common for your branch to fall behind the main branch. 

```
     B origin branch
    /
---X---A origin main
```

If you rebase your branch onto the main branch, resolving any conflicts, it might look like this:

```
         C origin branch
        /
---X---A origin main
```

However, after rebasing, if you try to update the origin branch from your local branch, it can result in a non-fast-forward situation.

Before rebasing, it looks like:

```
     B origin branch and local branch
    /   
---X---A origin main
```

After rebasing:

```
     B origin branch
    /   
---X---A origin main
        \
         C local branch (after rebasing)
```

To update the origin branch now, you must use `git push --force`, which can cause the loss of previous commits on the origin branch.

### Git Commit Amend Example

Operations like `git commit --amend` change history and can also create non-fast-forward scenarios.

Before the update:

```
     A local branch
    /
---X origin branch
```

After the update:

```
---X---A origin branch and local branch
```

If you amend the commit, the structure looks like this:

```
     B local branch
    /
---X---A origin branch
```

Even though B is a continuation of A, the fast-forward update fails. Instead, you’ll have to force the push:

```
---X---B origin branch and local branch
```

## Conclusions

Using `git push --force` is "dangerous" because it can lead to lost commits. However, sometimes it is unavoidable. It's crucial to understand what you're doing and communicate with your collaborators effectively when working on a non-main branch. For the origin main branch, non-fast-forward updates should always be avoided, as losing commits there can have significant repercussions.

---

# Git Squash Commits – Combining the Last N Commits into One

**Author:** Kolade Chris

If you are working on a project and trying to implement a new feature, you might commit your code a few times to test things out. This allows you to see how the code works or looks. However, as you progress, your commit history can get messy, as you may have several commits for changes that aren't necessary.

To fix this, you might want to combine all those commits into a single one. This process is called **commit squashing**.

## What is Commit Squashing?

Imagine you are cooking a stew and have added ingredients one by one. By the end, if you have too many containers on the table, you might decide to mix all those ingredients into a single pot. This simplifies the process and makes it easier to manage. In Git, squashing commits is similar: you take several small changes and combine them into one cleaner and more manageable commit.

## How to Squash Commits in Git with Interactive Rebase

In this process, you will use the `git rebase` command with the `-i` flag to combine your commits. This command allows you not only to squash commits but also to drop commits, reword commit messages, and add new files.

Let’s assume you have the following commits that you want to combine:

![Git Commands](link_to_your_image)

### 1. Check Your Commits

First, check how many commits you want to combine. Run the following command:

```bash
git log --oneline
```

### 2. Prepare for the Rebase

If you want to squash all the commits in your `new-feature` branch, you need to go back a number of commits, say, 6. Execute:

```bash
git rebase -i HEAD~6
```

This will open your text editor (the default is Vim, but in this case, it is VS Code).

### 3. Modify the Commits

In the editor, you will see something like this:

```
pick abcdef1 First commit
pick abcdef2 Second commit
pick abcdef3 Third commit
pick abcdef4 Fourth commit
pick abcdef5 Fifth commit
pick abcdef6 Sixth commit
```

Replace all the `pick` (or `p`) with `squash` (or simply `s`) except for the first one. This tells Git to combine those commits:

```
pick abcdef1 First commit
squash abcdef2 Second commit
squash abcdef3 Third commit
squash abcdef4 Fourth commit
squash abcdef5 Fifth commit
squash abcdef6 Sixth commit
```

### 4. Save and Close

After doing this, save the file and close it. Git will open another editor where you can see the new commit message it generates for you:

![Commit Message](link_to_your_image)

Here, you can delete all of them and add your custom message. Save and close again.

### 5. Check the Result

After completing the rebase, check your commit history again:

```bash
git log --oneline
```

You should see that all the commits have been combined into one with the new message:

![Commit History](link_to_your_image)

## How to Squash Commits with the Merge Command and the --squash Flag

You can also combine multiple commits into one when you are about to merge branches. This helps clean up the incoming branch of redundant commits. However, this option doesn’t give you as much control as the rebase.

### 1. Reset Your Commits

If you want to return to the previous commits, you can run:

```bash
git reset --hard HEAD@{7}
```

Then, check your log again.

### 2. Switch to the Main Branch

Switch to the main branch by executing:

```bash
git switch main
```

### 3. Merge and Squash

To merge the `new-feature` branch into `main` and squash the commits, use:

```bash
git merge --squash new-feature
```

If you check the Git log at this point, you won’t see any commits on the `new-feature` branch yet. But if you run `git status`, you will see changes ready to be committed.

### 4. Commit the Changes

Now, commit those changes with a suitable message. After this, run `git log --oneline` to ensure everything is in order.

## Conclusion

In this article, we learned how to squash multiple commits into one in two different ways. Regardless of the option you choose, the end goal of combining commits is achieved.

If you want more control over the process, you can use the rebase with the `-i` flag. But if you prefer a simpler method, you can squash commits while merging. Just be aware that with this option, you will need to commit your changes again.

---

# How to Squash Commits in Git

## Easy Guide to Squash Commit with Problem Solving

By Firda Sahidi

### Introduction

Squashing commits can be one of the tricky problems in software development, including iOS Development and many other projects. In this article, I’ll provide a simple tutorial on how to squash commits, along with problem-solving tips. Let’s explore this concept with an analogy that makes it easy to understand.

### Analogy: Making a Smoothie

Imagine you are making a smoothie. You have several ingredients: bananas, strawberries, yogurt, and honey. If you blend them all together without any preparation, you might end up with chunks of fruit instead of a smooth mixture. 

In Git, commits are like those chunks of fruit. If you have too many small commits, they can clutter your project history. Squashing commits is like blending your smoothie to create a smooth, cohesive drink that is easier to enjoy.

### Step-by-Step Guide to Squash Commits

1. **Checkout to the branch you want to squash.**
   ```bash
   git checkout <branch-name>
   // Example: git checkout develop
   ```

2. **Check how many commits you have in that branch.**
   ```bash
   git log
   ```

3. **Squash the commits.**
   ```bash
   git rebase -i HEAD~<number-of-commits>
   // Example: git rebase -i HEAD~2
   ```

4. **Pick which commits you want to squash.** In the editor that opens, type `squash` before the commit number you want to squash. For the commit you want to keep, type `pick`. It should look like this:

   ```
   pick 1a2b3c4 Commit message 1
   squash 2b3c4d5 Commit message 2
   ```

5. **Save and exit the editor.** Press `Esc`, then type `:wq` and hit Enter.

6. **Force push your changes.**
   ```bash
   git push -f
   ```

### Problem-Shooting

If you encounter merge conflict errors when squashing, don’t panic. You can fix errors easily using:

```bash
git mergetool
```

This command opens an external merge tool where you can resolve conflicts. Look for the red lines indicating errors, fix them, then press `Cmd + S` to save and exit the tool. Continue your squash with:

```bash
git rebase --continue
```

### Squash Tips

As a final tip, always squash your commits right after you make them. The more commits you have to squash into one, the higher the chance of conflicts. Make squashing a habit!

---

# Git Branching - Rebasing

## Understanding Rebasing

In Git, there are two primary ways to integrate changes from one branch into another: merging and rebasing. This section will explore rebasing, explaining what it is, how to do it, and why it’s an amazing tool.

### Analogy: Building a Lego Tower

Think of Git branching like building a Lego tower. You have two builders: one builds on the left side, and the other builds on the right side. 

When it’s time to combine the two sides, you can either merge (simply placing the two towers together) or rebase (taking pieces from the right tower and placing them on top of the left one to create a single, taller tower).

### The Basic Rebase Process

1. **Checkout to the branch you want to rebase.**
   ```bash
   git checkout experiment
   ```

2. **Rebase onto the master branch.**
   ```bash
   git rebase master
   ```

This process works by taking the changes from the commits on your branch and reapplying them on top of the master branch, creating a clean, linear history.

### Fast-Forward Merge

After rebasing, you can fast-forward the master branch:
```bash
git checkout master
git merge experiment
```

The end product remains the same, but rebasing gives you a clean history that appears as if all the work happened in sequence.

### More Complex Rebases

You can also rebase branches in more complex scenarios. For instance, if you have a topic branch off another topic branch, you can replay changes from one branch onto another using:

```bash
git rebase --onto master server client
```

This command takes the changes from the client branch that aren’t on the server and replays them on the master branch directly.

### The Risks of Rebasing

While rebasing is powerful, it has risks. **Never rebase commits that exist outside your repository and that others may have based their work on.** If you do, you might create confusion for your collaborators, as they will have to deal with rewritten commit histories.

### Conclusion

By using these concepts and analogies, you can grasp the mechanics of squashing commits and rebasing in Git. Remember, just like making a smoothie or building a Lego tower, the goal is to create something cohesive and easy to work with. Happy coding!

---

# Resolving Merge Conflicts Using the Command Line

## Navigation on the Platform
- **Mac**
- **Windows**
- **Linux**

## In this Article
- Merge conflicts due to competing line changes
- Merge conflicts due to deleted files
- Additional Reading

Merge conflicts occur when competing changes are made to the same line in a file, or when one person edits a file and another person deletes the same file. For more information, see "[About merge conflicts](https://docs.github.com/en/get-started/using-git/merging-branches#about-merge-conflicts)."

**Tip:** You can use the conflict editor in GitHub to resolve line change merge conflicts between branches that are part of a pull request. For more information, see "[Resolving a merge conflict on GitHub](https://docs.github.com/en/get-started/using-git/resolving-a-merge-conflict-on-github)."

## Merge Conflicts Due to Competing Line Changes

Imagine you're throwing a party and your friend is also throwing one. Both of you want to decide on the menu, but each has different ideas about what should be included. In the end, you have to come to an agreement for the party to be a success.

To resolve a merge conflict caused by competing line changes, you need to choose which changes to incorporate from the different branches into a new commit.

### Steps to Resolve Line Conflicts:

1. **Open Git Bash.**
2. **Navigate to the local repository that has the merge conflict.**
   ```bash
   cd REPOSITORY-NAME
   ```
3. **Generate a list of files affected by the merge conflict.**
   ```bash
   git status
   ```
   ```plaintext
   # On branch branch-b
   # You have unmerged paths.
   #   (fix conflicts and run "git commit")
   #
   # Unmerged paths:
   #   (use "git add <file>..." to mark resolution)
   #
   # both modified:      styleguide.md
   #
   # no changes added to commit (use "git add" and/or "git commit -a")
   ```

4. **Open your favorite text editor** (like Visual Studio Code) and navigate to the file that has merge conflicts.

5. **Look for the conflict marker `<<<<<<<`.** In your file, you'll see the changes from the base branch after the `<<<<<<< HEAD` line, then you'll see `=======`, which divides your changes from the changes in the other branch, followed by `>>>>>>> BRANCH-NAME`.

   ```plaintext
   If you have questions, please
   <<<<<<< HEAD
   open an issue
   =======
   ask in our IRC channel.
   >>>>>>> branch-a
   ```

6. **Decide which changes to keep.** You can keep just the changes from your branch, just the other branch's changes, or make a new change that incorporates changes from both branches. Remove the conflict markers and make any desired changes to the final merge:

   ```plaintext
   If you have questions, please open an issue or ask in our IRC channel if it's more urgent.
   ```

7. **Add or stage your changes.**
   ```bash
   git add .
   ```

8. **Commit your changes with a message.**
   ```bash
   git commit -m "Resolve merge conflict by incorporating both suggestions"
   ```

Now you can merge the branches in the command line or push your changes to your remote repository on GitHub and merge your changes in a pull request.

## Merge Conflicts Due to Deleted Files

Continuing with our party example, let’s say that while one of you is deciding what dishes to include, another decides that a dish should be removed from the menu. Here, too, you must agree whether to keep the dish or eliminate it.

### Steps to Resolve Conflicts for Deleted Files:

1. **Open Git Bash.**
2. **Navigate to the local repository that has the merge conflict.**
   ```bash
   cd REPOSITORY-NAME
   ```
3. **Generate a list of files affected by the merge conflict.**
   ```bash
   git status
   ```
   ```plaintext
   # On branch main
   # Your branch and 'origin/main' have diverged,
   # and have 1 and 2 different commits each, respectively.
   #  (use "git pull" to merge the remote branch into yours)
   # You have unmerged paths.
   #  (fix conflicts and run "git commit")
   #
   # Unmerged paths:
   #  (use "git add/rm <file>..." as appropriate to mark resolution)
   #
   # deleted by us:   README.md
   #
   # no changes added to commit (use "git add" and/or "git commit -a")
   ```

4. **Open your favorite text editor** and navigate to the file that has merge conflicts.

5. **Decide whether you want to keep the deleted file.** You might want to see the last changes made to the deleted file.

6. **To add the deleted file back to your repository:**
   ```bash
   git add README.md
   ```

7. **To remove this file from your repository:**
   ```bash
   git rm README.md
   ```

8. **Commit your changes with a message.**
   ```bash
   git commit -m "Resolve merge conflict by keeping the README.md file"
   ```

Now you can merge the branches in the command line or push your changes to your remote repository on GitHub and merge your changes in a pull request.

## Resolving Merge Conflicts in Visual Studio

When you merge one branch into another, changes in the files of commits from one branch may conflict with changes in the other. Git tries to automatically resolve these changes using the history in your repository to determine how the merged files should look. When it's not clear how to merge changes, Git stops the merge and notifies you about the files in conflict.

### Steps to Resolve Conflicts in Visual Studio:

1. **Preventing Merge Conflicts:**
   Git is good at automatically merging file changes in most cases, as long as the file's content doesn't change drastically between commits. If your branch is significantly behind the main branch, consider rebasing your branches before opening a pull request.

2. **Resolving Merge Conflicts:**
   If you collaborate with others on the same branch, you may see merge conflicts when pushing your changes.

   Visual Studio detects if the local branch you've been working on is behind its remote branch and gives you options to choose.

   ![Merge Options in Visual Studio](path/to/image.png)

   **Note:** If your remote repository supports "Force Push," you can enable it using `Git > Settings`.

   In this example, select **Pull** and then **Push** to include the changes introduced in the remote repository. If there are merge conflicts while pulling changes or trying to merge two branches, Visual Studio will notify you in the Git changes window.

   ![Merge Conflict Notification](path/to/image.png)

3. **Resolving the Conflicts:**
   The Git changes window shows a list of files with conflicts. To start resolving the conflicts, double-click a file or select **Open Merge Editor**.

   In the merge editor, you can start resolving your conflict using any of the following methods:
   - View your conflicts line by line and choose to keep either the right or left side by checking the checkboxes.
   - Select the **Take Incoming** button (or press F10) to accept all incoming changes, or the **Take Current** button (or press F11) to keep your current version of all conflicting changes. You can also do the same by selecting one of the checkboxes at the top of either side-by-side frame.
   - Manually edit your code in the Results window.

   ![Resolving Conflicts in Visual Studio](path/to/image.png)

4. **Finalizing the Resolution:**
   When you finish resolving the merge conflicts, select **Accept Merge**. Repeat this process for all files in conflict.

   Use the Git changes window to create a merge commit and resolve the conflict.

   ![Creating a Merge Commit](path/to/image.png)

   **Note:** If you want to keep all your changes in a file, you can right-click it in the unmerged changes section and select **Keep Current (Local)** without needing to open the merge editor.

5. **Configuring Your Comparison Tool:**
   If you configured your `.gitconfig` file to use a third-party comparison tool, you can open your comparison tool by selecting **Compare with Merge Tool** and choosing the tool you want to use.

   ![Configuring Comparison Tool](path/to/image.png)

   If you want to learn more about the comparison and merging tools that can be used with Visual Studio, check out "[Configuring an External Merge Tool for Git](https://learn.microsoft.com/en-us/visualstudio/version-control/configuring-external-merge-tools?view=vs-2019)."

---

# Git Cherry-Pick: Applying Changes from Existing Commits

## Overview

In the world of version control, sometimes you find a change in a commit that you want to apply to your current branch without merging the entire branch. This is where the `git cherry-pick` command comes into play. Think of it as picking a ripe fruit (the commit) from one branch and placing it in your basket (your current branch).

## SYNOPSIS

```bash
git cherry-pick [--edit] [-n] [-m <parent-number>] [-s] [-x] [--ff]
                 [-S[<keyid>]] <commit>…   
git cherry-pick (--continue | --skip | --abort | --quit)
```

## DESCRIPTION

When you use `git cherry-pick`, you apply the changes introduced by one or more existing commits to your current branch. Here's how it works:

1. **Clean Workspace**: Ensure your working directory is clean (no uncommitted changes). If your workspace resembles a messy kitchen, you won't be able to cook up those delicious changes.

2. **Creating New Commits**: For each commit you cherry-pick, Git creates a new commit in your current branch with the changes from the original commit. This is like copying a recipe and writing it in your own cookbook.

3. **Handling Conflicts**: If there are conflicts (like trying to mix two incompatible recipes), Git will keep track of them. Your current branch and HEAD pointer will remain at the last successful commit, while the problematic commit will be noted for you to resolve.

   - Conflicting changes will be marked in your files with conflict markers (`<<<<<<<` and `>>>>>>>`), indicating the parts that need attention. 

4. **Further Instructions**: For guidance on resolving conflicts, check the `git merge` documentation.

## OPTIONS

- `<commit>… `: Specifies the commits to cherry-pick. You can use various ways to refer to commits, including commit hashes or branch names.

- `-e` / `--edit`: Allows you to edit the commit message before committing.

- `--cleanup=<mode>`: Controls how the commit message is cleaned up before it's processed. Useful for managing commit messages during conflicts.

- `-x`: Appends a note in the commit message indicating which commit was cherry-picked. This is helpful for transparency when sharing the commit with others.

- `-m <parent-number>`: Used when cherry-picking a merge commit to specify the mainline parent.

- `-n` / `--no-commit`: Applies the changes without creating a commit. This is useful when applying multiple commits in one go.

- `-s` / `--signoff`: Adds a "Signed-off-by" line to the commit message.

- `--ff`: Performs a fast-forward if possible. If your branch is already at the parent of the cherry-picked commit, Git will just move the HEAD pointer.

- `--allow-empty`: Allows cherry-picking of empty commits.

- `--empty=(drop|keep|stop)`: Manages how to treat redundant commits already present in your history.

- `--strategy=<strategy>`: Specifies which merge strategy to use during cherry-picking.

- `--rerere-autoupdate`: Allows for automatic updates of the index after a resolution.

## SEQUENCER SUBCOMMANDS

These commands are used during an ongoing cherry-pick operation:

- `--continue`: Continues the operation after resolving conflicts.
- `--skip`: Skips the current commit and proceeds to the next.
- `--quit`: Cancels the current operation and resets the state.
- `--abort`: Reverts to the state before the cherry-pick began.

## EXAMPLES

- **Cherry-Pick the Latest Commit from Master**:
  ```bash
  git cherry-pick master
  ```
  This applies the latest commit from the `master` branch to your current branch.

- **Cherry-Pick Specific Commits**:
  ```bash
  git cherry-pick master~4 master~2
  ```
  This applies the changes from the fifth and third last commits on the `master` branch.

- **Applying Without Committing**:
  ```bash
  git cherry-pick -n master~1 next
  ```
  This applies changes to the working directory and index but doesn't create a new commit.

- **Backporting a Patch**:
  If you find that a patch doesn’t apply cleanly, you might do:
  ```bash
  git cherry-pick topic^
  git diff
  git cherry-pick --abort
  git cherry-pick -Xpatience topic^
  ```
  Here, you initially try to apply a change, check the differences, abort if it fails, and then try applying it again with a more careful strategy.

## Conclusion

Using `git cherry-pick` is like being a chef who selectively picks the best recipes to create a personalized menu for a dinner party. By understanding how to apply changes from other commits without bringing in unwanted ingredients (commits), you can maintain a clean and organized project history while still benefiting from others' contributions. Happy coding!