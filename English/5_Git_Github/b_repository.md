# About Repositories

A repository contains all your code, your files, and each file's revision history. You can discuss and manage your work within the repository.

## In this article

- About repositories
- Repository terminology
- About repository ownership
- About collaboration
- About repository visibility
- Next steps

## About Repositories

A repository is the most basic element of GitHub. It's a place where you can store your code, your files, and the revision history of each file. Think of a repository like a toolbox: inside, you keep all your tools (code and files) and also have a record of when you used each tool (revision history).

Repositories can have multiple collaborators and can be either public or private. You can create a new repository by going to [https://github.com/new](https://github.com/new). For instructions, see "Quickstart for repositories."

## Repository Terminology

Before getting started with repositories, learn these important terms.

| Term            | Definition                                                                                     |
|------------------|------------------------------------------------------------------------------------------------|
| **Branch**       | A parallel version of your code contained within the repository that does not affect the primary branch. Think of a branch like a limb of a tree that grows in a different direction but is still connected to the trunk. |
| **Clone**        | To download a full copy of a repository's data from GitHub.com, including all versions of every file and folder. It's like making a photocopy of an entire book. |
| **Fork**         | A new repository that shares code and visibility settings with the original "upstream" repository. It's like borrowing a recipe and adapting it to your style. |
| **Merge**        | To take changes from one branch and apply them to another. It's like combining two versions of a book to create a revised edition. |
| **Pull request** | A request to merge changes from one branch into another. Think of this as asking an editor to review and approve your changes to a manuscript. |
| **Remote**       | A repository stored on GitHub, not on your computer. Imagine it as a copy of your book that is kept in a library while you have the physical version. |
| **Upstream**     | The branch in an original repository that has been forked or cloned. The corresponding branch on the cloned or forked branch is called "downstream." It’s like the main river that gives rise to a tributary. |

## About Repository Ownership

You can own repositories individually or share ownership of repositories with other people in an organization. It's like having a house (repository) that you can own by yourself or share with friends.

In either case, access to repositories is managed by permissions. For more information, see "Permission levels for a personal account repository" and "Repository roles for an organization."

## About Collaboration

You can use repositories to manage your work and collaborate with others. It's like working on a group project: each member has their role and can contribute ideas.

- You can use **issues** to collect user feedback, report software bugs, and organize tasks you'd like to accomplish. For more information, see "About issues."
- You can use **GitHub Discussions** to ask and answer questions, share information, make announcements, and participate in conversations about a project. For more information, see "About discussions."
- You can use **pull requests** to propose changes to a repository. For more information, see "About pull requests."
- You can use **Projects** to organize and prioritize your issues and pull requests. For more information, see "About Projects."

With GitHub Free for personal accounts and organizations, you can work with unlimited collaborators on unlimited public repositories with a full feature set, or unlimited private repositories with a limited feature set. To get advanced tooling for private repositories, you can upgrade to GitHub Pro, GitHub Team, or GitHub Enterprise Cloud. For more information, see "GitHub’s plans."

## About Repository Visibility

You can restrict who has access to a repository by choosing a repository's visibility: public or private. It's like deciding whether you want your house to be visible to everyone or keep it closed off to a select group.

When you create a repository, you can choose to make it public or private. Repositories in organizations that use GitHub Enterprise Cloud and are owned by an enterprise account can also be created with internal visibility. For more information, see the GitHub Enterprise Cloud documentation.

- **Public repositories** are accessible to everyone on the internet.
- **Private repositories** are only accessible to you, the people you explicitly share access with, and, for organization repositories, certain organization members.
- Organization owners always have access to every repository created in an organization. For more information, see "Repository roles for an organization."

People with admin permissions for a repository can change an existing repository's visibility. For more information, see "Setting repository visibility."

---

# NAME
git-init - Create an empty Git repository or reinitialize an existing one

# SYNOPSIS
```bash
git init [-q | --quiet] [--bare] [--template=<template-directory>]
         [--separate-git-dir <git-dir>] [--object-format=<format>]
         [--ref-format=<format>]
         [-b <branch-name> | --initial-branch=<branch-name>]
         [--shared[=<permissions>]] [<directory>]
```

# DESCRIPTION
The `git init` command creates an empty Git repository—essentially a `.git` directory containing subdirectories for objects, refs/heads, refs/tags, and template files. An initial branch without any commits will be created (see the `--initial-branch` option below for its name).

If the `$GIT_DIR` environment variable is set, it specifies a path to use instead of `./.git` for the base of the repository.

If the object storage directory is specified via the `$GIT_OBJECT_DIRECTORY` environment variable, the SHA1 directories are created underneath; otherwise, the default `$GIT_DIR/objects` directory is used.

Running `git init` in an existing repository is safe. It will not overwrite things that are already there. The primary reason for rerunning `git init` is to pick up newly added templates (or to move the repository to another place if `--separate-git-dir` is given).

# OPTIONS
- `-q`
- `--quiet`
  Only print error and warning messages; all other output will be suppressed.

- `--bare`
  Create a bare repository. If `GIT_DIR` environment is not set, it is set to the current working directory.

- `--object-format=<format>`
  Specify the given object `<format>` (hash algorithm) for the repository. The valid values are `sha1` and (if enabled) `sha256`. `sha1` is the default.

  > Note: Currently, there is no interoperability between SHA-256 repositories and SHA-1 repositories.

- `--ref-format=<format>`
  Specify the given ref storage `<format>` for the repository. The valid values are:
  
  - `files` for loose files with packed-refs. This is the default.
  - `reftable` for the reftable format. This format is experimental, and its internals are subject to change.

- `--template=<template-directory>`
  Specify the directory from which templates will be used.

- `--separate-git-dir=<git-dir>`
  Instead of initializing the repository as a directory to either `$GIT_DIR` or `./.git/`, create a text file there containing the path to the actual repository. This file acts as a filesystem-agnostic Git symbolic link to the repository.

  If this is a reinitialization, the repository will be moved to the specified path.

- `-b <branch-name>`
- `--initial-branch=<branch-name>`
  Use `<branch-name>` for the initial branch in the newly created repository. If not specified, fall back to the default name (currently `master`, but this is subject to change in the future; the name can be customized via the `init.defaultBranch` configuration variable).

- `--shared[=(false|true|umask|group|all|world|everybody|<perm>)`
  Specify that the Git repository is to be shared amongst several users. This allows users belonging to the same group to push into that repository. When specified, the config variable `core.sharedRepository` is set so that files and directories under `$GIT_DIR` are created with the requested permissions. When not specified, Git will use permissions reported by `umask(2)`.

  The option can have the following values, defaulting to `group` if no value is given:
  
  - `umask` / `false`: Use permissions reported by `umask(2)`.
  - `group` / `true`: Make the repository group-writable. 
  - `all`, `world`, `everybody`: Same as group but make the repository readable by all users.
  - `<perm>`: `<perm>` is a 3-digit octal number prefixed with `0` and each file will have mode `<perm>`. 

By default, the configuration flag `receive.denyNonFastForwards` is enabled in shared repositories, so that you cannot force a non-fast-forwarding push into it.

If you provide a `<directory>`, the command is run inside it. If this directory does not exist, it will be created.

# TEMPLATE DIRECTORY
Files and directories in the template directory whose name do not start with a dot will be copied to the `$GIT_DIR` after it is created.

The template directory will be one of the following (in order):

1. The argument given with the `--template` option;
2. The contents of the `$GIT_TEMPLATE_DIR` environment variable;
3. The `init.templateDir` configuration variable; or
4. The default template directory: `/usr/share/git-core/templates`.

The default template directory includes some directory structure, suggested "exclude patterns" (see `gitignore`), and sample hook files.

The sample hooks are all disabled by default. To enable one of the sample hooks, rename it by removing its `.sample` suffix.

See `githooks` for more general info on hook execution.

# EXAMPLES
**Start a new Git repository for an existing code base:**
```bash
$ cd /path/to/my/codebase
$ git init      # (1)
$ git add .     # (2)
$ git commit    # (3)
```
1. Create a `/path/to/my/codebase/.git` directory.
2. Add all existing files to the index.
3. Record the pristine state as the first commit in the history.

# CONFIGURATION
Everything below this line in this section is selectively included from the `git-config` documentation. The content is the same as what’s found there:

- `init.templateDir`
  Specify the directory from which templates will be copied.

- `init.defaultBranch`
  Allows overriding the default branch name e.g., when initializing a new repository.

- `init.defaultObjectFormat`
  Allows overriding the default object format for new repositories.

- `init.defaultRefFormat`
  Allows overriding the default ref storage format for new repositories.

---

# Git Config: Customizing Your Git Environment

In this document, we'll take an in-depth look at the `git config` command. We briefly discussed `git config` usage on our Setting up a Repository page.

The `git config` command is like a settings menu for Git, where you can personalize your Git experience at a global or local project level. These configuration levels correspond to `.gitconfig` text files, and executing `git config` modifies these configuration files.

By understanding `git config` and the various settings available, you can create a powerful and customized Git workflow.

## Usage

The most basic use case for `git config` is to invoke it with a configuration name, which will display the set value for that name. Think of configuration names as labels in a filing cabinet, where each label helps you find the right file. For example: 

```bash
git config user.email
```

In this example, `email` is a sub-property of the `user` configuration block. This command will return the configured email address, if any, that Git will associate with locally created commits.

## Git Config Levels and Files

Before diving deeper, let's understand configuration levels. The `git config` command can accept arguments to specify which configuration level to operate on. Here are the available configuration levels:

- **Local**: This is like a personal diary; it applies only to the specific project you're working on. Local configuration values are stored in a file within the repository’s `.git` directory: `.git/config`.

- **Global**: This is like a user profile; it applies to the entire user on your operating system. Global configuration values are stored in a file located in the user's home directory (`~/.gitconfig` on Unix systems and `C:\Users\<YourUser>\.gitconfig` on Windows).

- **System**: This is akin to a community rule; it applies across the entire machine for all users and all repositories. The system-level configuration file lives in a specific location on the system (`$(prefix)/etc/gitconfig` on Unix systems and `C:\ProgramData\Git\config` on Windows Vista and newer).

The order of priority for configuration levels is: **local**, **global**, **system**. This means that when Git looks for a configuration value, it starts at the local level and then checks the global and system levels if it doesn't find it.

## Writing a Value

Now let's see how to write a configuration value:

```bash
git config --global user.email "your_email@example.com"
```

This command writes the value `your_email@example.com` to the configuration name `user.email`, applying it globally for the current operating system user.

### Setting the Default Editor

Many Git commands will launch a text editor to prompt for further input. Configuring which editor Git should use is a common use case for `git config`. Here’s a quick table of popular editors and their corresponding Git commands:

| Editor              | Config Command                                      |
|---------------------|-----------------------------------------------------|
| Atom                | `git config --global core.editor "atom --wait"`    |
| emacs               | `git config --global core.editor "emacs"`          |
| nano                | `git config --global core.editor "nano -w"`        |
| vim                 | `git config --global core.editor "vim"`            |
| Sublime Text (Mac) | `git config --global core.editor "subl -n -w"`     |
| Sublime Text (Win, 32-bit install) | `git config --global core.editor "'c:/program files (x86)/sublime text 3/sublimetext.exe' -w"` |
| Sublime Text (Win, 64-bit install) | `git config --global core.editor "'c:/program files/sublime text 3/sublimetext.exe' -w"` |
| Textmate            | `git config --global core.editor "mate -w"`       |

## Merge Tools

In the event of a merge conflict, Git will launch a "merge tool." By default, Git uses its built-in tool, but you can specify an external merge tool with:

```bash
git config --global merge.tool kdiff3
```

## Colored Outputs

Git supports colored terminal output, which can help you quickly read Git output. You can customize your Git output to use a personalized color theme using `git config`.

The `color.ui` variable is the master switch for Git colors. Setting it to `false` will disable all colored output:

```bash
git config --global color.ui false
```

By default, `color.ui` is set to `auto`, meaning it applies colors only to immediate terminal output.

### Git Color Values

In addition to `color.ui`, there are many other granular color settings. Here are some key ones:

1. **color.branch**: Configures the output color of the `git branch` command.
2. **color.diff**: Applies colors to `git diff`, `git log`, and `git show` output.
3. **color.status**: Applies color to the `git status` command output.

You can specify colors using simple names like `red`, `green`, or hexadecimal color codes like `#ff0000`.

## Aliases

Aliases are custom shortcuts that can save you time when using Git. For example, you can create an alias for the `git commit` command:

```bash
git config --global alias.ci commit
```

Now you can use `git ci` instead of `git commit`. Aliases can also reference other aliases:

```bash
git config --global alias.amend ci --amend
```

This command creates an `amend` alias that combines the `ci` alias with the `--amend` flag.

## Formatting & Whitespace

Git has several "whitespace" features that can be configured to highlight whitespace issues. Common configurations include:

- `blank-at-eol`: Highlights orphan whitespaces at the line endings.
- `space-before-tab`: Highlights spaces before tab characters.

You can enable or disable these features based on your preferences.

## Summary

In this article, we covered the use of the `git config` command. We discussed how it serves as a convenient method for editing raw Git configuration files on your filesystem. Key takeaways include:

- How to configure your Git editor.
- Understanding configuration levels.
- Customizing Git colors.
- Creating aliases for commands.

Overall, `git config` is a powerful helper tool that allows you to personalize your Git environment and streamline your workflow. Understanding these configuration options is essential for setting up a repository effectively.

---

# Customizing Git - Git Configuration

So far, we’ve covered the basics of how Git works and how to use it. In this chapter, we’ll explore how to make Git operate in a more customized fashion by introducing several important configuration settings and the hooks system. With these tools, it's easy to get Git to work exactly the way you, your company, or your group needs it to.

## Git Configuration

Just like customizing your workspace for maximum productivity, Git allows you to specify configuration settings with the `git config` command. One of the first things you did was set up your name and email address:

```bash
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

Now, let’s dive into some interesting options that you can set to customize your Git usage.

### Configuration Levels

Git uses a series of configuration files to determine non-default behavior. Think of these levels like different layers of clothing you wear based on the weather:

1. **System-wide settings**: The first place Git looks for configuration values is in the system-wide `/etc/gitconfig` file. These settings apply to every user on the system and all of their repositories. If you pass the `--system` option to `git config`, it reads and writes from this file specifically.

2. **User-specific settings**: The next place Git looks is the `~/.gitconfig` (or `~/.config/git/config`) file, which is specific to each user. You can make Git read and write to this file by passing the `--global` option.

3. **Repository-specific settings**: Finally, Git looks for configuration values in the Git directory (`.git/config`) of whatever repository you’re currently using. These values are specific to that single repository and represent passing the `--local` option to `git config`. If you don’t specify which level you want to work with, this is the default.

Each of these “levels” (system, global, local) overrides values in the previous level, so values in `.git/config` take precedence over those in `/etc/gitconfig`.

**Note:** Git’s configuration files are plain text, so you can also set these values by manually editing the file. However, it’s generally easier to use the `git config` command.

### Basic Client Configuration

The configuration options recognized by Git fall into two categories: **client-side** and **server-side**. Most of the options are client-side, configuring your personal working preferences. If you want to see a list of all options your version of Git recognizes, you can run:

```bash
$ man git-config
```

This command provides a detailed list of all available options. 

**Note:** For advanced use cases, you may want to look up "Conditional includes" in the documentation.

### Common Configuration Options

#### 1. `core.editor`

By default, Git uses your default text editor (set via the `VISUAL` or `EDITOR` environment variables) to create and edit commit messages. To change the default editor, use the `core.editor` setting:

```bash
$ git config --global core.editor emacs
```

Now, whenever you commit, Git will open Emacs, regardless of your default shell editor.

#### 2. `commit.template`

This option allows you to set a template for commit messages. For example, consider a template file at `~/.gitmessage.txt` that looks like this:

```
Subject line (try to keep under 50 characters)

Multi-line description of commit,
feel free to be detailed.

[Ticket: X]
```

To use it as the default message when you commit, set the `commit.template` configuration value:

```bash
$ git config --global commit.template ~/.gitmessage.txt
```

When you run `git commit`, your editor will open with the template, helping you remember to format your message properly.

#### 3. `core.pager`

This setting determines which pager Git uses to display output like logs and diffs. You can change it from the default `less` to your preferred pager or turn it off entirely:

```bash
$ git config --global core.pager ''
```

With this, Git will print the entire output of all commands, regardless of length.

#### 4. `user.signingkey`

If you’re making signed annotated tags, set your GPG signing key as a configuration setting to simplify the process:

```bash
$ git config --global user.signingkey <gpg-key-id>
```

Now, you can sign tags without specifying your key every time.

#### 5. `core.excludesfile`

You can ignore certain files across all repositories by creating a global `.gitignore` file. For example, if you create a file at `~/.gitignore_global` with the contents:

```
*~
.*.swp
.DS_Store
```

You can set it with:

```bash
$ git config --global core.excludesfile ~/.gitignore_global
```

Git will then ignore these files in all your repositories.

#### 6. `help.autocorrect`

If you mistype a command, Git will suggest the correct command. If you set `help.autocorrect` to `1`, Git will automatically run the command for you after a brief pause:

```bash
$ git chekcout master
```

Git might display a message like this:

```
WARNING: You called a Git command named 'chekcout', which does not exist.
Continuing under the assumption that you meant 'checkout'
in 0.1 seconds automatically...
```

### Colors in Git

Git supports colored terminal output, which helps in quickly parsing command output. You can customize this behavior with the following options:

- **`color.ui`**: This is the master switch for colored output. To turn it off, run:

    ```bash
    $ git config --global color.ui false
    ```

  The default is `auto`, which colors output when sent to a terminal but omits color codes when redirected.

- **`color.*`**: Git allows for verb-specific coloring. You can set options like `color.branch`, `color.diff`, and `color.status` to `true`, `false`, or `always`.

For instance, to set the meta information in your diff output to blue text, run:

```bash
$ git config --global color.diff.meta "blue black bold"
```

### External Merge and Diff Tools

Git has built-in diff capabilities, but you can configure it to use external tools like P4Merge for a graphical interface. Here’s how to set it up:

1. Download P4Merge from Perforce.
2. Create a merge wrapper script named `extMerge` that calls the P4Merge binary:

    ```bash
    #!/bin/sh
    /Applications/p4merge.app/Contents/MacOS/p4merge "$@"
    ```

3. Create a diff wrapper script named `extDiff` that uses the merge script:

    ```bash
    #!/bin/sh
    [ $# -eq 7 ] && /usr/local/bin/extMerge "$2" "$5"
    ```

4. Make both scripts executable:

    ```bash
    $ sudo chmod +x /usr/local/bin/extMerge
    $ sudo chmod +x /usr/local/bin/extDiff
    ```

5. Configure Git to use your custom tools:

    ```bash
    $ git config --global merge.tool extMerge
    $ git config --global mergetool.extMerge.cmd 'extMerge "$BASE" "$LOCAL" "$REMOTE" "$MERGED"'
    $ git config --global mergetool.extMerge.trustExitCode false
    $ git config --global diff.external extDiff
    ```

Now, when you run `git diff`, P4Merge will open, allowing for a visual comparison.

### Conclusion

Customizing Git enhances your productivity and allows you to tailor the tool to fit your workflow better. By understanding and utilizing these configuration options, you can streamline your Git usage and make it work in harmony with your development style.

---

# Git vs Working Directory – Understand the Difference

The **Working Directory** and the **Git Directory** are repositories (folders) for storing files, but they operate in different ways. Here are the key distinctions between them.

## Creator of a Git vs. Working Directory

- **Working Directory**: This is a folder you create to store all the files of your project. Think of it as your **workspace** where you organize your tools and materials.
  
- **Git Directory**: This is a folder that Git creates within the working directory you specified to monitor. It’s like a **hidden storage room** where Git keeps track of important changes you’ve made.

## Visibility

- **Git Directory**: This is a hidden folder. Imagine it as a **back room** in your office that’s out of sight but contains important items.
  
- **Working Directory**: This is a normal folder. It’s like the **desktop** of your office where you can see everything you need at a glance.

## Use of a Git vs. Working Directory

- **Git Directory**: It records the versions of the files you authorized Git to track. It’s like a **logbook** that keeps track of every significant change.
  
- **Working Directory**: It can store any type of file. It can contain files (or folders) that are under version control and those that aren’t. It’s like a **storage area** where you keep both items in use and items not in use.

## Location

- You can create a **Working Directory** anywhere on your system. It’s like deciding where you want to set up your office.
  
- Git creates the **Git Directory** within a working repository. So, if your office is the working directory, the Git directory is like the **basement** of that office.

## Content of a Git vs. Working Directory

- **Working Directory**: Contains both **tracked** and **untracked** files. It’s like a **filing cabinet** that has organized items and others that are not, but all are present.
  
- **Git Directory**: Contains only **tracked** files. It’s like a **safe** where only important documents are stored.

---

# Introduction - What is Git?

## What is Git?

So, what is Git in a nutshell? This is an important section to understand because if you grasp what Git is and the fundamentals of how it works, using Git effectively will be much easier for you. As you learn Git, try to clear your mind of things you might know about other Version Control Systems (VCS), like CVS, Subversion, or Perforce; doing so will help you avoid subtle confusions when using the tool. While the user interface of Git is quite similar to that of these other VCS, Git stores and thinks about information in a very different way, and understanding these differences will help you avoid confusion while using it.

## Snapshots, Not Deltas

The main difference between Git and any other VCS (including Subversion and similar) is the way Git thinks about its data. Conceptually, most other systems store information as a list of changes based on files. These systems (CVS, Subversion, Perforce, etc.) think of the information they store as a set of files and the changes made to each file over time (this is commonly referred to as delta-based version control).

**Storing data as changes to a base version of each file**  
Imagine that each time you edit a document, only the **difference** between the previous document and the new one is saved. This is what other VCS do.

But Git doesn’t think or store its data this way. Instead, Git thinks of its data more like a series of **snapshots** of a miniature filesystem. Every time you commit or save the state of your project, Git essentially takes a **picture** of how all your files look at that moment and stores a reference to that snapshot. To be efficient, if files haven’t changed, Git doesn’t store the file again, just a link to the identical file it has already stored. Git thinks of its data more like a **flow of snapshots**.

**Git stores data as snapshots of the project over time**  
This is an important distinction between Git and almost all other VCS. This makes Git rethink almost every aspect of version control that most other systems copied from the previous generation. This makes Git resemble more of a **mini filesystem** with some incredibly powerful tools built on top of it, rather than just being a VCS.

## Almost Every Operation is Local

Most operations in Git only require local files and resources to operate; generally, no information from another computer on your network is needed. If you’re used to a **CVCS** where most operations have that network latency, this aspect of Git will make you feel like the gods of speed have blessed Git with supernatural powers. Because you have the entire history of the project right there on your local disk, most operations feel almost instantaneous.

For example, to browse the history of the project, Git doesn’t need to go to the server to fetch the history and display it for you; it simply reads it directly from your local database. This means you see the project history almost instantly. If you want to see the changes introduced between the current version of a file and the file from a month ago, Git can look up the file from a month ago and do a local diff calculation, rather than having to ask a remote server to do it or downloading a previous version of the file from the remote server to do it locally.

This also means there’s very little you can’t do if you’re offline or outside the VPN. If you hop on a plane or a train and want to do a bit of work, you can happily commit (to your local copy, remember) until you get a network connection to push your changes. If you get home and can’t get your VPN client to work properly, you can still work. In many other systems, doing this is almost impossible or painful. For instance, in Perforce, you can’t do much when you’re not connected to the server; in Subversion and CVS, you can edit files but you can’t commit changes to your database (because your database is offline). This might not seem like a big deal, but you’d be surprised at the significant difference it can make.

## Git has Integrity

Everything in Git is verified before it is stored and then referenced by that checksum. This means it’s impossible to change the content of any file or directory without Git knowing about it. This functionality is built into Git at the lowest levels and is integral to its philosophy. You can’t lose information in transit or suffer file corruption without Git being able to detect it.

The mechanism Git uses for this verification is called a **SHA-1 hash**. This is a 40-character string composed of hexadecimal characters (0–9 and a–f) and is calculated based on the content of a file or directory structure in Git. A SHA-1 hash looks something like this:

```
24b9da6552252987aa493b52f8696cd6d3b00373
```

You’ll see these hash values everywhere in Git because they’re used a lot. In fact, Git stores everything in its database not by the filename, but by the hash value of its content.

## Git Generally Only Adds Data

When you perform actions in Git, almost all of them only add data to Git’s database. It’s hard to make the system do anything that isn’t reversible or that deletes data in some way. Just like with any VCS, you can lose or mess up changes that you haven’t committed yet, but after you’ve committed a snapshot in Git, it’s very hard to lose it, especially if you regularly push your database to another repository.

This makes using Git a pleasure because we know we can experiment without the danger of severely messing things up. For a deeper look into how Git stores its data and how you can recover data that seems lost, check out "Undoing Things."

## The Three States

Now pay attention: here’s the main thing you should remember about Git if you want the rest of your learning process to flow smoothly. Git has three main states in which your files can reside: **modified**, **staged**, and **committed**:

- **Modified**: Means you’ve changed the file, but haven’t committed it to your database yet.
  
- **Staged**: Means you’ve marked a modified file in its current version to go into your next commit snapshot.
  
- **Committed**: Means the data is securely stored in your local database.

This leads us to the concepts of **staging area** and **commit**. The staging area is where you place your files before committing the changes.

```plaintext
+-----------------+    +------------------+
|    Modified     | -> |      Staged      |
|                 |    |                  |
+-----------------+    +------------------+
                           |
                           |
+-------------------------+-----------------------+
|                       Committed                  |
| (Data securely stored in Git's local database)    |
+---------------------------------------------------+
```

## Conclusion

With this foundation about what Git is, you will be better prepared to understand the commands and workflows you’ll use later. Remember that Git is a powerful tool that will allow you to manage your code efficiently and effectively.

---

# Git Commit

## What is a Git Commit?

The `git commit` command creates a commit, which is like a snapshot of your repository. Imagine your repository is a photo album, and each commit is a photo capturing a specific moment in time. These commits are snapshots of your repository at particular points in time. You should make new commits frequently, based on logical units of change. Over time, commits should tell the story of your project's evolution and how it became what it is today. Commits include many metadata in addition to the content and message, such as the author, timestamp, and more.

## How Git Commit Works

Commits are the building blocks of "save points" within Git's version control. Using `git commit` allows you to shape your project's history intentionally and safely. You can make commits on different branches and specify exactly which changes you want to include. Commits are created on the branch currently checked out (where HEAD is pointing), so it's always a good idea to run `git status` before making a commit to ensure you're on the correct branch. Before making a commit, you'll need to stage the changes you want to include in the commit using `git add [file]`.

Commits are lightweight SHA hashes, objects within Git. Whenever you work with text files, you don't need to worry about how many files you have, how large they are, or how many commits you make. Git can handle it!

## Committing in Two Stages

Commits have two stages that help you create commits correctly. Commits should be logical and atomic units of change representing a specific idea. But, not everyone works the same way. You might get excited and end up resolving two or three issues before remembering to commit. That's okay! Git can handle that. Once you're ready to create your commits, you'll use `git add <FILENAME>` to specify the files you want to "stage" for the commit. Without adding files, the `git commit` command won't work. Git only checks the staging area to see what to include in the commit. Staging or adding files can be done through the command line and also with most Git interfaces like GitHub Desktop by selecting the lines or files you want to stage.

You can also use a helpful command, `git add -p`, to review changes and separate them, even if they are in the same file.

## How to Use Git Commit

### Common Uses and Options for Git Commit

- `git commit`: This command initiates the commit process, but since it doesn’t include a -m option for the message, it will open your default text editor for you to create the commit message. If you haven't set anything, there's a good chance this will be VI or Vim. (To exit, press Esc, then :wq and then Enter.)
  
- `git commit -m "descriptive commit message"`: This command initiates the commit process and allows you to include the commit message at the same time.
  
- `git commit -am "descriptive commit message"`: In addition to including the commit message, this option lets you skip the staging phase. The -a addition automatically stages any files that are already being tracked by Git (changes in files you've already committed before).

- `git commit --amend`: Replaces the most recent commit with a new one. (More on this later!)

To see all the possible options you have with `git commit`, check out the Git documentation.

## How to Undo Commits in Git

Sometimes, you may need to change history. Perhaps you need to undo a commit. If you find yourself in this situation, there are a few very important things to remember:

- If you're "undoing" a commit that exists on the remote, you could create big problems for your collaborators.
- Undoing a commit on work you only have locally is much safer.

### What Can Go Wrong When Changing History?

Changing history for collaborators can be problematic in various ways. Imagine: you and another collaborator have the same repository, with the same history. But, they make a change that removes the most recent commit. They continue making new commits from the previous commit. Meanwhile, you keep working with the commit the collaborator tried to delete. When they push, they will have to 'force push', which should alert them that they are changing history. What do you think will happen when you try to push?

In dramatic cases, Git might decide that the histories are too different, and the projects are no longer related. This is uncommon, but a big problem.

The most common result is that your `git push` would bring back the "deleted" commit to the shared history. (First, you'd have to do `git pull` if you were working on the same branch and then merge, but the results would be the same.) This means that what was so important to delete is now back in the repository. A password, token, or large binary file could come back without ever notifying you.

## git revert

`git revert` is the safest way to change history with Git. Instead of removing existing commits, `git revert` reviews the changes introduced in a specific commit and then applies the inverse of those changes in a new commit. It acts like a "commit undo" command, without sacrificing the integrity of your repository's history. `git revert` is always the recommended way to change history when possible.

## git reset

Sometimes, a commit includes sensitive information that really needs to be removed. `git reset` is a very powerful command that can cause you to lose work. When you reset, you move the HEAD pointer and branch pointer back to another point in time, making it seem as if the intermediate commits never happened. Before using `git reset`:

- Be sure to talk to your team about any shared commits.
- Research the three types of reset to see which one is right for you (`--soft`, `--mixed`, `--hard`).
- Confirm any work you don’t want to lose intentionally: committed work can be recovered, but uncommitted work cannot.

## git reflog

If you're changing history and undoing commits, you should know about `git reflog`. If you get into trouble, the reflog might save you. The reflog is a record of every commit that HEAD has pointed to. For example, if you use `git reset` and accidentally lose commits, you can find and access them with `git reflog`.

## Updating Commits with Git Commit Amend

While `git commit --amend` changes history, it only modifies the most recent commit on your current branch. This can be an extremely useful command for commits that:

- Have not been pushed to the remote yet.
- Have a typo in the commit message.
- Do not contain the changes you would like them to contain.

### Examples of Git Commit

Once you've staged the files you want to include in your commit, you're ready. Whether you're committing in a tool like GitHub Desktop or through your command line, the commit message is important. Commit messages should be brief and descriptive of your change. If you're reviewing the history of your repository, commit messages will guide you, so they should tell a story. Commands for commits in the command line can include the message in the following format:

```bash
git commit -m "example commit message"
```

Commit messages should be present tense and directive, such as the following examples:

```bash
git commit -m "create file structure for Git guides"
git commit -m "translate Git cheat sheet to German"
git commit -m "update broken URL to Git resources"
```

If you want to include more context in your commit messages, you can also add an extended commit message.

### Related Commands

- `git add [file]`: Stages the file for versioning, adding it to the staging area.
- `git status`: It’s always a good idea. This command shows you which branch you're on, which files are in the working directory or staging area, and any other important information.
- `git push`: Uploads all commits from the local branch to the remote.
- `git log`: Navigates and inspects the evolution of the project files.

---

# gitignore - Specify intentionally untracked files to ignore

## SYNOPSIS

`$XDG_CONFIG_HOME/git/ignore`, `$GIT_DIR/info/exclude`, `.gitignore`

## DESCRIPTION

A `.gitignore` file specifies intentionally untracked files that Git should ignore. Files already tracked by Git are unaffected; see the NOTES below for details.

Each line in a `.gitignore` file specifies a pattern. When deciding whether to ignore a file, Git compares it against each pattern in order until one matches.

You can use comments in `.gitignore` files to maintain clarity. These begin with a `#` and continue to the end of the line.

## SAMPLE .gitignore FILE

```gitignore
# build files
/build/
/dist/

# IDE output files
*.log
*.class

# copy files
*.swp

# ignore a specific file
config/database.yml

# ignore all files in a directory
temp/*
```

## CREATING A .gitignore FILE

To create a `.gitignore` file, simply create a text file in the root of your repository and name it `.gitignore`. You can open it with any text editor and start adding the patterns you want to ignore.

## NOTES

Files that are already being tracked by Git will not be affected by the rules in `.gitignore`. To stop tracking a file that is already in the repository, you must first remove it with `git rm --cached [file]` and then add the file to your `.gitignore`.

### Ignoring Directories

To ignore an entire directory, simply place a slash at the end of the directory name:

```gitignore
# Ignore directory
logs

/
```

### Ignoring Files by Extension

You can ignore all files of a specific type using the wildcard character `*`. For example, to ignore all `.log` files, you would use:

```gitignore
# Ignore log files
*.log
```

---

## CONCLUSION

Learning about `git commit` and how to use it correctly is essential for any developer. Make sure to create meaningful commits and use the `.gitignore` file to keep your repository clean and organized. Always communicate with your team when you need to change your repository's history and use `git revert` or `git reflog` when necessary.

---

# Git Basics - Viewing the Commit History

## Viewing the Commit History

Once you have created several commits or cloned a repository with an existing commit history, you’ll likely want to review what has transpired. The most basic and powerful tool for this is the `git log` command.

### Analogy: A Diary of Changes

Think of your Git repository as a diary that records every change you make to your project. Each entry in this diary represents a commit, detailing what you changed, why you changed it, and when. Just like you would flip through your diary to recall past events, the `git log` command allows you to view the commit history.

### Getting Started with Git Log

To begin, let’s clone a simple project called “simplegit.” You can do this by running:

```bash
$ git clone https://github.com/schacon/simplegit-progit
```

When you run `git log` in this project, you should see output that looks something like this:

```bash
$ git log
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Mar 17 21:52:11 2008 -0700

    Change version number

commit 085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 16:40:33 2008 -0700

    Remove unnecessary test

commit a11bef06a3f659402fe7563abf99ad00de2209e6
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 10:31:28 2008 -0700

    Initial commit
```

### Understanding the Output

By default, the `git log` command lists the commits made in reverse chronological order; that is, the most recent commits appear first. Each commit entry includes the following details:
- **SHA-1 checksum:** A unique identifier for the commit.
- **Author's name and email:** Information about who made the commit.
- **Date:** When the commit was made.
- **Commit message:** A brief description of what changes were made.

### More Options for Exploring History

There are many options for the `git log` command that can help you find exactly what you’re looking for. Here are some useful ones:

1. **Show Differences with `-p` or `--patch`:**
   This option shows the changes introduced in each commit.

   ```bash
   $ git log -p -2
   ```

2. **Summarize Changes with `--stat`:**
   This option provides statistics on modified files.

   ```bash
   $ git log --stat
   ```

3. **Custom Output Format with `--pretty`:**
   This option allows you to change the log output format.

   ```bash
   $ git log --pretty=oneline
   ```

### Analogy: Customizing Your Diary

Just like you might want to organize your diary entries by date or highlight specific events, `git log` offers options to customize how you view the commit history. This customization helps you find information quickly and effectively.

### Useful Specifiers for Custom Formats

When using the `--pretty=format` option, you can specify how to display the output. Here are some useful specifiers:

| Specifier | Description of Output               |
|-----------|-------------------------------------|
| `%H`      | Commit hash                         |
| `%h`      | Abbreviated commit hash             |
| `%an`     | Author name                         |
| `%ae`     | Author email                        |
| `%s`      | Subject (commit message)           |

### Filtering the Log Output

In addition to formatting options, `git log` also provides limiting options to narrow down your commit view. Here are some useful commands:

- **Last n commits:** To show only the last n commits, use `-<n>`. For example, to see the last 2 commits:

  ```bash
  $ git log -2
  ```

- **Commits by Date:** Use `--since` and `--until` to filter commits based on time.

  ```bash
  $ git log --since=2.weeks
  ```

- **Search by Author or Keyword:** You can filter commits based on the author or keywords in commit messages using `--author` and `--grep`.

  ```bash
  $ git log --author="Scott Chacon" --grep="test"
  ```

### Analogy: Finding Specific Entries

Imagine searching through your diary for entries by a particular date or about a specific event. Git’s filtering options allow you to do just that, making it easier to find relevant commits among many.

### Conclusion

The `git log` command is a powerful tool for viewing the history of changes in your Git repository. By understanding the output and utilizing the various options, you can effectively track your project's evolution and find specific changes when needed. Just as a well-organized diary can help you recall important moments, a well-managed Git log can provide insights into your project's development.