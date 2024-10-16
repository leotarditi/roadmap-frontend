# Git Branching - Basic Branching and Merging

## Basic Branching and Merging

Let’s go through a simple example of branching and merging with a workflow that you might use in the real world. You’ll follow these steps:

1. Do some work on a website.
2. Create a branch for a new user story you’re working on.
3. Do some work in that branch.
4. At this stage, you’ll receive a call that another issue is critical and you need a hotfix. You’ll do the following:
   - Switch to your production branch.
   - Create a branch to add the hotfix.
5. After it’s tested, merge the hotfix branch, and push to production.
6. Switch back to your original user story and continue working.

## Basic Branching

Let’s say you’re working on your project and have a couple of commits already on the `master` branch.

### A Simple Commit History

![A simple commit history](url_to_image) 

You’ve decided that you’re going to work on issue #53 in whatever issue-tracking system your company uses. To create a new branch and switch to it at the same time, you can run the `git checkout` command with the `-b` switch:

```bash
$ git checkout -b iss53
Switched to a new branch "iss53"
```

This is shorthand for:

```bash
$ git branch iss53
$ git checkout iss53
```

### Creating a New Branch Pointer

![Creating a new branch pointer](url_to_image) 

You work on your website and do some commits. Doing so moves the `iss53` branch forward because you have it checked out (that is, your HEAD is pointing to it):

```bash
$ vim index.html
$ git commit -a -m 'Create new footer [issue 53]'
```

### The `iss53` Branch Has Moved Forward with Your Work

![The iss53 branch has moved forward with your work](url_to_image) 

Now you get the call that there is an issue with the website, and you need to fix it immediately. With Git, you don’t have to deploy your fix along with the `iss53` changes you’ve made, and you don’t have to put a lot of effort into reverting those changes before you can work on applying your fix to what is in production. All you have to do is switch back to your `master` branch.

However, before you do that, note that if your working directory or staging area has uncommitted changes that conflict with the branch you’re checking out, Git won’t let you switch branches. It’s best to have a clean working state when you switch branches. There are ways to get around this (namely, stashing and commit amending) that we’ll cover later on in Stashing and Cleaning. For now, let’s assume you’ve committed all your changes, so you can switch back to your `master` branch:

```bash
$ git checkout master
Switched to branch 'master'
```

At this point, your project working directory is exactly the way it was before you started working on issue #53, and you can concentrate on your hotfix. This is an important point to remember: when you switch branches, Git resets your working directory to look like it did the last time you committed on that branch. It adds, removes, and modifies files automatically to make sure your working copy is what the branch looked like on your last commit to it.

Next, you have a hotfix to make. Let’s create a hotfix branch on which to work until it’s completed:

```bash
$ git checkout -b hotfix
Switched to a new branch 'hotfix'
$ vim index.html
$ git commit -a -m 'Fix broken email address'
[hotfix 1fb7853] Fix broken email address
 1 file changed, 2 insertions(+)
```

### Hotfix Branch Based on `master`

![Hotfix branch based on master](url_to_image) 

You can run your tests, make sure the hotfix is what you want, and finally merge the hotfix branch back into your `master` branch to deploy to production. You do this with the `git merge` command:

```bash
$ git checkout master
$ git merge hotfix
Updating f42c576..3a0874c
Fast-forward
 index.html | 2 ++
 1 file changed, 2 insertions(+)
```

You’ll notice the phrase “fast-forward” in that merge. Because the commit C4 pointed to by the branch hotfix you merged in was directly ahead of the commit C2 you’re on, Git simply moves the pointer forward. To phrase that another way, when you try to merge one commit with a commit that can be reached by following the first commit’s history, Git simplifies things by moving the pointer forward because there is no divergent work to merge together — this is called a “fast-forward.”

Your change is now in the snapshot of the commit pointed to by the `master` branch, and you can deploy the fix.

### `master` is Fast-Forwarded to `hotfix`

![master is fast-forwarded to hotfix](url_to_image) 

After your super-important fix is deployed, you’re ready to switch back to the work you were doing before you were interrupted. However, first you’ll delete the hotfix branch, because you no longer need it — the `master` branch points at the same place. You can delete it with the `-d` option to `git branch`:

```bash
$ git branch -d hotfix
Deleted branch hotfix (3a0874c).
```

Now you can switch back to your work-in-progress branch on issue #53 and continue working on it.

```bash
$ git checkout iss53
Switched to branch "iss53"
$ vim index.html
$ git commit -a -m 'Finish the new footer [issue 53]'
[iss53 ad82d7a] Finish the new footer [issue 53]
1 file changed, 1 insertion(+)
```

### Work Continues on `iss53`

![Work continues on iss53](url_to_image) 

It’s worth noting here that the work you did in your hotfix branch is not contained in the files in your `iss53` branch. If you need to pull it in, you can merge your `master` branch into your `iss53` branch by running `git merge master`, or you can wait to integrate those changes until you decide to pull the `iss53` branch back into `master` later.

## Basic Merging

Suppose you’ve decided that your issue #53 work is complete and ready to be merged into your `master` branch. In order to do that, you’ll merge your `iss53` branch into `master`, much like you merged your hotfix branch earlier. All you have to do is check out the branch you wish to merge into and then run the `git merge` command:

```bash
$ git checkout master
Switched to branch 'master'
$ git merge iss53
Merge made by the 'recursive' strategy.
index.html |    1 +
1 file changed, 1 insertion(+)
```

This looks a bit different than the hotfix merge you did earlier. In this case, your development history has diverged from some older point. Because the commit on the branch you’re on isn’t a direct ancestor of the branch you’re merging in, Git has to do some work. In this case, Git does a simple three-way merge, using the two snapshots pointed to by the branch tips and the common ancestor of the two.

### Three Snapshots Used in a Typical Merge

![Three snapshots used in a typical merge](url_to_image) 

Instead of just moving the branch pointer forward, Git creates a new snapshot that results from this three-way merge and automatically creates a new commit that points to it. This is referred to as a merge commit, and is special in that it has more than one parent.

### A Merge Commit

![A merge commit](url_to_image) 

Now that your work is merged in, you have no further need for the `iss53` branch. You can close the issue in your issue-tracking system and delete the branch:

```bash
$ git branch -d iss53
```

## Basic Merge Conflicts

Occasionally, this process doesn’t go smoothly. If you changed the same part of the same file differently in the two branches you’re merging, Git won’t be able to merge them cleanly. If your fix for issue #53 modified the same part of a file as the hotfix branch, you’ll get a merge conflict that looks something like this:

```bash
$ git merge iss53
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

Git hasn’t automatically created a new merge commit. It has paused the process while you resolve the conflict. If you want to see which files are unmerged at any point after a merge conflict, you can run `git status`:

```bash
$ git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")

Unmerged paths:
  (use "git add <file>..." to mark resolution)

    both modified:      index.html

no changes added to commit (use "git add" and/or "git commit -a")
```

Anything that has merge conflicts and hasn’t been resolved is listed as unmerged. Git adds standard conflict-resolution markers to the files that have conflicts, so you can

 see what the conflicting changes are:

```html
<h2>Contact Us</h2>
<<<<<<< HEAD
<p>Please use the following email address to contact us:</p>
<p>email@example.com</p>
=======
<p>We’d love to hear from you!</p>
<p>contact@example.com</p>
>>>>>>> iss53
```

You can then edit the file to resolve the conflict. After resolving the conflict, you need to stage the changes and commit them:

```bash
$ git add index.html
$ git commit -m 'Merge issue #53 changes'
```

### Summary

Branching in Git allows for a lot of flexibility in managing code. You can switch between different branches to work on different features or bug fixes without affecting the main production code. Merging integrates those changes back into the main line of development. However, conflicts may arise, and understanding how to resolve them is crucial for a smooth workflow.

In summary, remember these key points:
- Branches help you manage features, bug fixes, and experiments.
- Merges can be fast-forward or require a three-way merge.
- Conflicts may arise during merging, and knowing how to resolve them is essential.

By practicing these concepts, you’ll become more comfortable with branching and merging in Git, making your development process much more efficient.

---

# Git Branch - List, Create, or Delete Branches

## Introduction

In the world of Git, branches are like separate paths in a forest. When you want to explore a new route without disturbing your main path (the master branch), you create a new branch. This way, you can try out new ideas, fix bugs, or add features without affecting the stable version of your project.

## SYNOPSIS

```bash
git branch [--color[=<when>] | --no-color] [--show-current]
	[-v [--abbrev=<n> | --no-abbrev]]
	[--column[=<options>] | --no-column] [--sort=<key>]
	[--merged [<commit>]] [--no-merged [<commit>]]
	[--contains [<commit>]] [--no-contains [<commit>]]
	[--points-at <object>] [--format=<format>]
	[(-r | --remotes) | (-a | --all)]
	[--list] [<pattern>… ]
git branch [--track[=(direct|inherit)] | --no-track] [-f]
	[--recurse-submodules] <branchname> [<start-point>]
git branch (--set-upstream-to=<upstream> | -u <upstream>) [<branchname>]
git branch --unset-upstream [<branchname>]
git branch (-m | -M) [<oldbranch>] <newbranch>
git branch (-c | -C) [<oldbranch>] <newbranch>
git branch (-d | -D) [-r] <branchname>… 
git branch --edit-description [<branchname>]
```

## DESCRIPTION

The `git branch` command is your guide for managing branches. Here’s what it does:

### Listing Branches

If you run `git branch` without any options, you’ll see a list of your branches. Think of this as looking at a map of the forest, with your current path highlighted in green and marked with an asterisk. If you have branches checked out in linked worktrees, those will be shown in cyan and marked with a plus sign.

- **Example**: `git branch` will show you all available branches.

### Creating a New Branch

When you want to start a new adventure, you create a new branch using:

```bash
git branch <branchname>
```

This is like picking a new path to explore. However, it won’t automatically switch you to this new path; you’ll need to use `git switch <newbranch>` to actually start walking down it.

### Tracking Branches

When you create a branch from a remote-tracking branch, Git sets up a tracking configuration. This is akin to placing signs along your new path to let you know which way to go when you want to return to the main road.

- **Example**: Use the `--track` option to set up tracking information:
  
```bash
git branch --track <branchname> <start-point>
```

### Renaming a Branch

If you decide a branch needs a better name, you can rename it using:

```bash
git branch -m <oldbranch> <newbranch>
```

Think of this as updating the signpost along your path to something more descriptive.

### Deleting a Branch

Once you’ve completed your exploration and no longer need a path, you can delete the branch:

```bash
git branch -d <branchname>
```

Just make sure the path (branch) is fully merged into the main road (upstream branch), or it will refuse to delete it.

## OPTIONS

- `-d`, `--delete`: Remove a branch. The branch must be fully merged.
- `-D`: Force deletion of a branch, even if it hasn’t been merged.
- `-m`, `--move`: Rename a branch, preserving its config and history.
- `-c`, `--copy`: Copy a branch to a new name, keeping its config and history.
- `-r`, `--remotes`: List or delete remote-tracking branches.
- `-a`, `--all`: Show both local and remote branches.
- `-v`, `-vv`, `--verbose`: Show additional information when listing branches.
- `--contains`, `--no-contains`: List branches that do or do not contain a specific commit.

## Conclusion

Using `git branch` is essential for effective version control in your projects. By understanding how to create, manage, and delete branches, you can navigate through your codebase like a skilled explorer, ensuring that your main path remains stable while you experiment and innovate.

---

# Guide to Branches in GitHub

## Renaming a Branch

Renaming a branch is a simple process that can be done by anyone with write permissions in the repository. However, if the branch is the default or a protected branch, only administrators can perform this action.

### Who Can Use This Feature?

People with write permissions can rename branches, but they cannot do so with the default or protected branches. Administrators can rename any branch, including default and protected branches.

### In This Article

- About Renaming Branches
- Renaming a Branch
- Updating a Local Clone After a Branch Name Changes

### About Renaming Branches

Renaming a branch on GitHub is like changing the name of a road on a map. When you do this, all links that contain the old branch name are automatically redirected to the new name. It’s important to know that if you renamed a branch that was in an open pull request, that pull request will be closed.

### Renaming a Branch

To rename a branch on GitHub:

1. Go to the main page of the repository.
2. In the file tree view on the left, select the branch dropdown menu and then click "View all branches."
3. Next to the branch you want to rename, select the dropdown menu and click "Rename branch."
4. Type a new name for the branch.
5. Review the information about local environments and then click "Rename branch."

### Updating a Local Clone After a Branch Name Changes

Once you’ve renamed a branch on GitHub, any collaborator with a local clone of the repository will need to update their clone. To do this, run the following commands in your terminal:

```bash
git branch -m OLD-BRANCH-NAME NEW-BRANCH-NAME
git fetch origin
git branch -u origin/NEW-BRANCH-NAME NEW-BRANCH-NAME
git remote set-head origin -a
```

Optionally, you can run the following command to remove tracking references to the old branch name:

```bash
git remote prune origin
```

---

## Creating and Deleting Branches Within Your Repository

You can create or delete branches directly on GitHub. Here’s how to do it.

### Creating a Branch

You can create a branch in different ways on GitHub. Imagine you are creating a new path in the forest; you need to choose a good name so others know where it leads.

#### Creating a Branch via the Branches Overview

1. Go to the main page of the repository.
2. In the file tree view on the left, select the branch dropdown menu and then click "View all branches."
3. Click "New branch."
4. Type a name for the new branch.
5. Choose a source for your branch (if your repository is a fork, select the corresponding repository).
6. Click "Create branch."

#### Creating a Branch Using the Branch Dropdown

1. Go to the main page of the repository.
2. Select the branch dropdown menu.
3. If you want to create a new branch from a branch other than the default, select that other branch first.
4. In the "Find or create a branch..." text field, type a unique name for your new branch and click "Create branch."

### Deleting a Branch

Deleting a branch is like clearing a path in the forest when you no longer need it. But make sure it’s not in use.

1. Go to the main page of the repository.
2. From the file tree view on the left, select the branch dropdown menu and click "View all branches."
3. Next to the branch you want to delete, click the trash can icon.
4. If the branch is associated with at least one open pull request, those pull requests will close. Read the warning and click "Delete."

Remember, if the branch you want to delete is the default branch of the repository, you must first choose a new default branch before deleting it.

## Conclusion

Managing branches in GitHub is essential for an efficient workflow. Understanding how to rename, create, and delete branches will help you keep your project organized and on track. Think of branches as paths in a forest: some lead to interesting places, while others can be removed when they are no longer useful.

---

# Git Checkout - Switch Branches or Restore Working Tree Files

## SYNOPSIS
```bash
git checkout [-q] [-f] [-m] [<branch>]
git checkout [-q] [-f] [-m] --detach [<branch>]
git checkout [-q] [-f] [-m] [--detach] <commit>
git checkout [-q] [-f] [-m] [[-b|-B|--orphan] <new-branch>] [<start-point>]
git checkout [-f] <tree-ish> [--] <pathspec>… 
git checkout [-f] <tree-ish> --pathspec-from-file=<file> [--pathspec-file-nul]
git checkout [-f|--ours|--theirs|-m|--conflict=<style>] [--] <pathspec>… 
git checkout [-f|--ours|--theirs|-m|--conflict=<style>] --pathspec-from-file=<file> [--pathspec-file-nul]
git checkout (-p|--patch) [<tree-ish>] [--] [<pathspec>… 
```

## DESCRIPTION
The `git checkout` command is like a remote control for your project. It allows you to switch between different channels (branches) or revert back to a specific episode (commit) in your project's history.

### Basic Usage
- **Switching Channels (Branches)**  
  ```bash
  git checkout <branch>
  ```  
  Imagine you are watching a TV show with different seasons. Each branch represents a different season. If you want to switch to a different season (branch), you can use `git checkout <branch>`. This command updates your working files to match the current state of that branch while keeping your changes safe.

- **Creating and Switching to a New Channel (Branch)**  
  ```bash
  git checkout -b <new-branch>
  ```  
  If you want to create a new season and start watching it from a specific episode, you can use `-b` to create and switch to a new branch. It’s like launching a new show based on your favorite episodes.

### Detaching HEAD
- **Detaching HEAD**  
  ```bash
  git checkout --detach <commit>
  ```  
  Think of HEAD as the TV remote pointer. When you detach it, you can browse previous episodes without changing the show you are currently watching. This is useful for inspecting older commits without altering your main story.

### Overwriting Files
- **Restoring Files**  
  ```bash
  git checkout <pathspec>
  ```  
  If you've changed a scene in the movie (file) and want to restore it to the original, use this command to overwrite the current version with the one from your index or specified commit. It’s like hitting the "reset" button on your remote to go back to the original version.

### Interactive Mode
- **Selecting Changes**  
  ```bash
  git checkout -p
  ```  
  With the `-p` option, you can interactively choose which parts of a scene you want to keep or discard. It’s like editing a movie clip, allowing you to pick and choose what stays in the final cut.

## OPTIONS
- `-q`, `--quiet`: Suppresses feedback messages.
- `-f`, `--force`: Forces the switch, discarding any changes in your working directory. It's like telling the remote to ignore any changes you've made to the channel.
- `--ours`, `--theirs`: In case of a conflict, these options allow you to choose which version of the file to keep, as if you are choosing which actor’s performance you want in the final edit.

### Creating New Branches
- `-b <new-branch>`: Creates a new branch.
- `-B <new-branch>`: Creates a new branch or resets an existing one.

### Tracking Branches
- `--track`: Sets up upstream tracking for new branches, as if you are subscribing to a new season for updates.
- `--no-track`: Prevents tracking for new branches.

### Special Cases
- `--orphan <new-branch>`: Creates a new branch with no history. It’s like starting a completely new show that doesn’t connect with any of your previous seasons.

## CONCLUSION
The `git checkout` command is a versatile tool that lets you manage your project like a TV show, switching between branches, restoring files, and even creating new stories. Understanding how to use it effectively is essential for any frontend developer as you navigate the various versions of your projects.