# Git and GitHub: Essentials for Microsoft Learn Documentation

As a contributor to Microsoft Learn documentation, you will interact with multiple tools and processes. You will work alongside other collaborators on the same project, potentially on the same content, even at the same time. All of this is made possible by Git and GitHub software.

Git is an open-source version control system. It facilitates this type of project collaboration through distributed version control of files residing in repositories. Essentially, Git enables the integration of workflows performed by multiple contributors over time for a given repository.

GitHub is a web-based hosting service for Git repositories, like those used to store Microsoft Learn content. For any project, GitHub houses the main repository from which collaborators can make copies for their own work.

## Key Concepts

### Branch

Branches separate workflows (typically referred to as versions). Contributions are always made and limited to a specific branch.

Imagine you are in a meeting where each working group is discussing a different project. Each group has its own whiteboard (branch) to make their notes without interfering with others. As they progress, they can integrate their ideas (changes) into a main whiteboard (default branch).

In practice, depending on the type of work you do, you may end up with several branches in your repository. It is not uncommon to work on multiple branches at the same time, each representing a different project.

### Fork

This term is commonly used as a noun to refer to a copy of a main GitHub repository. In practice, a fork is just another repository. But it is special in that GitHub maintains a connection back to the parent repository. Sometimes it is used as a verb, as in "You first need to fork the repository."

### Git

If you are familiar with centralized version control systems (like Team Foundation Server, SharePoint, or Visual SourceSafe), you will notice that Git has a unique workflow and contribution terminology to support its distributed model. For example, there is no file locking typically associated with check-in/check-out operations. Instead, Git concerns itself with changes at a finer level, comparing files byte by byte.

Git uses a hierarchical structure to store and manage the content of a project:

- **Repository**: Also known as "repo," this is the highest unit of storage. A repository contains one or more branches.
- **Branch**: A unit of storage that contains the files and folders that make up a project's content.

Contributors interact with Git to update and manipulate repositories both locally and on GitHub:

- **Locally** through tools like the Git Bash console, which supports Git commands to manage local repositories and communicate with GitHub repositories.
- **Through www.github.com**, which integrates Git to manage the reconciliation of contributions flowing back into the main repository.

### GitHub

> **Note**: While the documentation guidelines are based on the use of GitHub, some teams use Visual Studio Team Services to host Git repositories. The Visual Studio Team Explorer client provides a graphical interface to interact with Team Services repositories as an alternative to using Git commands through a command line.

All workflows start and end at the GitHub level, where the main repository for any documentation project is stored. The copies created by collaborators for their own use are distributed across multiple computers. These copies will eventually be reconciled back into the project's main GitHub repository.

## Directory Organization

The default branch of a project serves as the current version of the content. The content in the default branch (and branches created from it) is flexibly aligned with the organization of articles on the corresponding pages of Microsoft Learn. Subdirectories are used to separate similar articles (like services), multimedia content (like image files), and "inclusion" files (which allow for content reuse).

### Article Subdirectory

Typically, you can find a main article directory from the root of the repository. This directory contains a set of subdirectories. Articles in the subdirectories are formatted as Markdown files that use a .md extension. Some repositories that support multiple services use a generic /articles subdirectory, like the Azure-Docs repository. Others may use a specific service name, such as the IntuneDocs repository, which uses /IntuneDocs.

Within the root of this directory, you may find general articles that relate to the overall service or product. Typically, you will then find another series of subdirectories that match the common features/services or scenarios. For example, the Azure "virtual machines" articles are in the /virtual-machines subdirectory.

### Multimedia Subdirectory

Each article directory contains a /media subdirectory for the corresponding multimedia files. The multimedia files contain images used by articles that have references to images.

### Inclusion Subdirectory

Whenever we have reusable content that is shared in two or more articles, it is placed in an /includes subdirectory outside the main article directory. In a Markdown file that uses the inclusion file, a corresponding "include" directive is placed in the location where the inclusion file needs to be referenced.

## Markdown File Template

For convenience, the root of each repository typically contains a Markdown template file called template.md. You can use this template file as a "starting file" if you need to create a new article for submission to the repository. The file contains:

- A metadata header at the top of the file, delimited by two lines of 3 dashes. It contains various tags used to track information related to the article.
- A metadata section that describes the various tags and metadata values. If you are unsure of the values to use for the metadata section, you can leave them blank or comment them out with a hash symbol (#), and they will be reviewed/completed by the pull request reviewer for the repository.

## Origin

This term is the name assigned to the connection between your local repository and the repository from which it was cloned. In the Microsoft Learn workflow, origin represents the connection to your fork. This term is sometimes used as a nickname for the upstream repository itself, as in "Remember to push your changes to origin."

## Pull Requests

A pull request (PR) is a request for a content owner to pull your changes into the official source. A PR allows the collaborative model of GitHub by asking for the changes (also known as commits) from your working branch to be pulled and merged into another branch. In most cases, that other branch is the default branch in the main repository.

## Remote

A remote is a named connection to a remote repository, such as the "origin" or "upstream" remote. Git refers to this as remote because it is used to refer to a repository that is hosted on another computer.

## Upstream

Similar to the origin remote, upstream is a named connection to another repository. In the Microsoft Learn workflow, upstream represents the connection between your local repository and the main repository from which your fork was created. This term is sometimes used as a nickname for the upstream repository itself, as in "Remember to pull the latest changes from upstream."

## Learn More

If you're not familiar with Git or GitHub, these resources can help you learn, be productive, or answer questions.

- [Git Version Control Resources](https://git-scm.com/book/en/v2)
- [Pro Git eBook (web)](https://git-scm.com/book/en/v2)
- [Pro Git eBook (PDF)](https://git-scm.com/book/en/v2)
- [Codecademy Learn Git Course](https://www.codecademy.com/learn/learn-git)
- [GitHub Guides](https://guides.github.com/)
- [GitHub Learning Resources](https://github.com/)

## Frequently Asked Questions

### What is Git?

Git helps keep track of changes when many people work on computer code together. It's like a time machine for code, so you can see what changed and go back if needed.

### Why use Git?

It's great for teamwork. Git makes it easy for many people to work on the same project without interfering with each other's work. It also helps easily fix mistakes.

### How does Git work?

Git stores all versions of a project's code. When you make changes, Git takes a picture (like a snapshot) of what's different. You can make different versions at the same time and then merge them later.

### What is GitHub?

GitHub is a website where you can store your Git projects. It's like a public library where everyone can see your code and help you improve it.

### How do I get started with Git and GitHub?

Start by creating an account on GitHub and learning some basic Git commands. Then you can start working on your own projects or contributing to others'.

## Conclusion

Using Git and GitHub is like having a superpower for collaboration on projects. You can track changes, work with others seamlessly, and make your content on Microsoft Learn better every day. Learning to use these tools will help you be more efficient and effective in your work. Start exploring today!

---

# Hello World

Follow this Hello World exercise to learn GitHub's pull request workflow.

## In this article
- Introduction
- Step 1: Create a repository
- Step 2: Create a branch
- Step 3: Make and commit changes
- Step 4: Open a pull request
- Step 5: Merge your pull request
- Conclusion
- Next steps
- Further reading

## Introduction
This tutorial teaches you GitHub essentials like repositories, branches, commits, and pull requests. You'll create your own Hello World repository and learn GitHub's pull request workflow, a popular way to create and review code.

In this quickstart guide, you will:
- Create and use a repository.
- Start and manage a new branch.
- Make changes to a file and push them to GitHub as commits.
- Open and merge a pull request.

## Prerequisites
You must have a GitHub account. For more information, see "Creating an account on GitHub."

You don't need to know how to code, use the command line, or install Git (the version control software that GitHub is built on).

## Step 1: Create a repository
The first thing we'll do is create a repository. You can think of a repository as a **box** where you keep related items, such as files, images, videos, or even other boxes. Just like a box can contain various tools for a specific project, a repository groups together items that belong to the same "project" or thing you're working on.

Often, repositories include a **README file**, which is a document that describes your project. README files are written in **Markdown**, an easy-to-read and easy-to-write language for formatting plain text. In the next tutorial, "Setting up your profile," we'll learn more about Markdown.

GitHub lets you add a README file at the same time you create your new repository. GitHub also offers other common options such as a license file, but you do not have to select any of them now.

Your `hello-world` repository can be a place where you store ideas, resources, or even share and discuss things with others.

1. In the upper-right corner of any page, select `+`, then click **New repository**.
2. In the "Repository name" box, type `hello-world`.
3. In the "Description" box, type a short description. For example, type "This repository is for practicing the GitHub Flow."
4. Select whether your repository will be **Public** or **Private**.
5. Select **Add a README file**.
6. Click **Create repository**.

## Step 2: Create a branch
Branching lets you have different versions of a repository at one time.

By default, your repository has one branch named `main` that is considered the definitive branch. You can create additional branches off of `main` in your repository.

Think of a branch like a **side road** on a journey. When you take a side road, you can explore new scenery without altering your main path. Branching is helpful when you want to add new features to a project without changing the main source of code. The work done on different branches will not show up on the main branch until you merge it.

When you create a branch off the main branch, you're making a copy, or **snapshot**, of `main` as it was at that point in time. If someone else made changes to the main branch while you were working on your branch, you could pull in those updates.

**Creating a branch:**
1. Click the **Code** tab of your `hello-world` repository.
2. Above the file list, click the dropdown menu that says `main`.
3. Type a branch name, `readme-edits`, into the text box.
4. Click **Create branch: readme-edits from main**.

Now you have two branches, `main` and `readme-edits`. Right now, they look exactly the same. Next, you'll add changes to the new `readme-edits` branch.

## Step 3: Make and commit changes
When you created a new branch in the previous step, GitHub brought you to the code page for your new `readme-edits` branch, which is a copy of `main`.

You can make and save changes to the files in your repository. On GitHub, saved changes are called **commits**. Each commit has an associated **commit message**, which is a description explaining why a particular change was made. Commit messages capture the history of your changes so that other contributors can understand what you’ve done and why.

1. Under the `readme-edits` branch you created, click the `README.md` file.
2. To edit the file, click the pencil icon (✏️).
3. In the editor, write a bit about yourself.
4. Click **Commit changes**.
5. In the "Commit changes" box, write a commit message that describes your changes.
6. Click **Commit changes**.

These changes will be made only to the README file on your `readme-edits` branch, so now this branch contains content that's different from `main`.

## Step 4: Open a pull request
Now that you have changes in a branch off of `main`, you can open a **pull request**.

Pull requests are the heart of collaboration on GitHub. When you open a pull request, you're proposing your changes and requesting that someone review and pull in your contribution and merge them into their branch. Pull requests show **diffs**, or differences, of the content from both branches. The changes, additions, and subtractions are shown in different colors.

As soon as you make a commit, you can open a pull request and start a discussion, even before the code is finished.

1. Click the **Pull requests** tab of your `hello-world` repository.
2. Click **New pull request**.
3. In the Example Comparisons box, select the branch you made, `readme-edits`, to compare with `main` (the original).
4. Look over your changes in the diffs on the Compare page, make sure they're what you want to submit.
5. Click **Create pull request**.
6. Give your pull request a title and write a brief description of your changes. You can include emojis and drag and drop images and gifs.
7. Click **Create pull request**.

### Reviewing a pull request
When you start collaborating with others, this is the time you'd ask for their review. This allows your collaborators to comment on or propose changes to your pull request before you merge the changes into the main branch.

We won't cover reviewing pull requests in this tutorial, but if you're interested in learning more, see "About pull request reviews." Alternatively, try the GitHub Skills "Reviewing pull requests" course.

## Step 5: Merge your pull request
In this final step, you will merge your `readme-edits` branch into the `main` branch. After you merge your pull request, the changes on your `readme-edits` branch will be incorporated into `main`.

Think of merging as **bringing the side road back to the main highway**. Sometimes, a pull request may introduce changes to code that conflict with the existing code on `main`. If there are any conflicts, GitHub will alert you about the conflicting code and prevent merging until the conflicts are resolved.

1. At the bottom of the pull request, click **Merge pull request** to merge the changes into `main`.
2. Click **Confirm merge**. You will receive a message that the request was successfully merged, and the request was closed.
3. Click **Delete branch**. Now that your pull request is merged and your changes are on `main`, you can safely delete the `readme-edits` branch. If you want to make more changes to your project, you can always create a new branch and repeat this process.
4. Click back to the **Code** tab of your `hello-world` repository to see your published changes on `main`.

## Conclusion
By completing this tutorial, you've learned to create a project and make a pull request on GitHub.

As part of that, we've learned how to:
- Create a repository.
- Start and manage a new branch.
- Change a file and commit those changes to GitHub.
- Open and merge a pull request.

## Next steps
Explore further and practice more with GitHub features.

## Further reading
- [GitHub Documentation](https://docs.github.com)
- [Markdown Guide](https://www.markdownguide.org)

---

# Creating an Account on GitHub

Create a personal account to get started with GitHub.

## In this article
- About your personal account on GitHub
- Signing up for a new personal account
- Next steps
- Further reading

## About your personal account on GitHub
To get started with GitHub, you'll need to create a free personal account and verify your email address.

Every person who uses GitHub signs in to a user account. Your user account is your identity on GitHub and has a username and profile. For example, you can see @octocat's profile.

Think of your GitHub account as your **identity card** in the world of development. Just like an ID card identifies you in real life, your account identifies you in the developer community. Later, you can explore the different types of accounts that GitHub offers and decide if you need a billing plan. For more information, see "Types of GitHub accounts" and "GitHub’s plans."

Note that the steps in this article don't apply to Enterprise Managed Users. If your GitHub account has been created for you by your company, you can skip this article and continue to "Hello World."

## Signing up for a new personal account
To create your account, follow these steps:

1. Navigate to [https://github.com/](https://github.com/).
2. Click **Sign up**.
3. Follow the prompts to create your personal account.

During sign up, you'll be asked to verify your email address. Without a verified email address, you won't be able to complete some basic GitHub tasks, such as creating a repository.

Verifying your email address is like **activating your credit card**. Even though the card exists, you won't be able to use it until you activate it. If you're having problems verifying your email address, there are some troubleshooting steps you can take. For more information, see "Verifying your email address."

## Next steps
Once you've created and verified your account, you'll be ready to start exploring GitHub. The next step will be to learn how to create your first repository, which is like creating a **toolbox** where you will store all your projects.

## Further reading
- [GitHub Documentation](https://docs.github.com)
- [Guide to Verifying Your Email Address](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/verifying-your-email-address)

---

# Setting Up Your Profile

Your profile tells people who you are and what you care about.

## In this article
- About your profile
- Adding a profile picture and bio
- Adding a profile README
- Next steps
- Further reading

## About your profile
Your GitHub profile page is a place where people can learn more about you. You can use your profile to:

- Share your interests and skills.
- Showcase your projects and contributions.
- Express your identity and show the GitHub community who you are.

Think of your profile as a **digital resume**. Just like a resume showcases your skills and experiences, your GitHub profile allows you to display your projects and what you’re passionate about. In this tutorial, you will learn to customize your profile by adding a profile picture, a bio, and a profile README.

You will also learn the basics of Markdown syntax, which you will use to format any writing you do on GitHub.

### Prerequisites
You need to have a GitHub account. For more information, see "Creating an account on GitHub".

## Adding a Profile Picture and Bio
First, let’s add an image to your profile. Your profile picture helps others identify you across GitHub.

### Adding a Profile Picture
1. In the upper right corner of any page, click your existing profile avatar and then, from the dropdown menu, click **Settings**.
2. In "Profile Picture," select **Edit**, then click **Upload a new picture...**.
3. Choose an image and click **Upload**.
4. Crop your image.
5. Click **Set new profile picture**.

Your profile picture is like your **signature** in the digital world. It helps people recognize and remember your work.

### Adding a Bio
On your profile page, below your profile picture, click **Edit profile**.

1. In "Bio," write one or two sentences about yourself, such as who you are and what you do.

**Note:** Keep the bio short; we will add a longer description of your interests in your profile README in the next section.

2. To add an emoji to your bio, visit the "Emoji Cheat Sheet" and copy and paste an emoji into the "Bio" dialog box.
3. Optionally, add your preferred pronouns, workplace, location, time zone, and any links to your personal website and social accounts. Your pronouns will only be visible to users who are logged in to GitHub.
4. Click **Save**.

## Adding a Profile README
Next, we will create a special repository and a README file that will be displayed directly on your profile page.

Your profile README contains information such as your interests, skills, and background, and can be a great way to introduce yourself to others on GitHub and showcase your work.

Just as we learned in the "Hello World" tutorial, README.md files are written using Markdown syntax (note the .md extension), which is just a way to format plain text.

In the following steps, we will create and edit your profile README.

### Step 1: Create a New Repository for Your Profile README
1. In the upper right corner of any page, select the plus sign (+) and then click **New repository**.
2. In "Repository name," enter a name that matches your GitHub username. For example, if your username is "octocat," the repository name must be "octocat."
3. Optionally, in the "Description" field, write a description of your repository. For example, "My personal repository."
4. Select **Public**.
5. Select **Initialize this repository with a README**.
6. Click **Create repository**.

### Step 2: Edit the README.md File
1. Click the pencil icon next to your profile README.
2. In the "Edit" view, you will see some pre-filled text to start with. On line 1, remove the text that says ### Hello everyone and write # About Me.

   In Markdown syntax, ### turns plain text into a small heading ("third level"), while ## or # turn it into second and first level headings respectively.
   
3. Switch to "Preview" to see how the text is rendered now. You should see the new text displayed as a much larger heading.
4. Switch back to "Edit."
5. Remove line 3 and line 16. 

   This HTML syntax (for example, `<!--`) keeps the other lines hidden when you switch to "Preview."
   
6. Fill out some of the prompts in lines 8 to 15 and delete any line you don’t want. For example, add your interests, skills, hobbies, or a fun fact about yourself.
7. Now, switch to "Preview." You should see your completed prompts rendered as a bulleted list.
8. Switch back to "Edit" and remove any other lines of text you do not wish to display on your profile.

Continue personalizing and editing your profile README. 

- Use the "Emoji Cheat Sheet" to add emojis.
- Use the "Markdown Cheat Sheet" to experiment with additional Markdown formatting.

### Step 3: Publish Your Changes to Your Profile
When you are satisfied with how your profile README looks in "Preview" and you are ready to publish it, click **Commit changes...**.

1. In the dialog that opens, simply click **Commit changes** again.
2. Navigate back to your profile page. You will see your new profile README displayed on your profile.

## Next Steps
Now that you have set up your profile, it’s time to start exploring more about GitHub and how you can contribute to open-source projects or create your own.

## Further Reading
- [GitHub Documentation](https://docs.github.com)
- [Guide to Using Markdown](https://www.markdownguide.org/)

---

# Managing Your Profile README

You can add a README to your GitHub profile to tell other people about yourself.

## Who Can Use This Feature?
Profile READMEs are not available to managed user accounts.

## In This Article
- About Your Profile README
- Prerequisites
- Adding a Profile README
- Removing a Profile README
- Further Reading

## About Your Profile README
You can share information about yourself with the community on GitHub by creating a profile README. GitHub displays your profile README at the top of your profile page.

You decide what information to include in your profile README, giving you full control over how you present yourself on GitHub. Here are some examples of information that visitors may find interesting, fun, or useful in your profile README:

- An "About Me" section that describes your work and interests.
- Contributions you're proud of, and context about those contributions.
- Guidance for getting help in communities where you're involved.

Think of your README as a **billboard** at the entrance of an event. Just like a billboard can attract people by describing what they can expect, your README showcases your skills and passions to visitors on your profile.

You can format text and include emojis, images, and GIFs in your profile README using Markdown. For more information, see ["Getting Started with Writing and Formatting on GitHub."](https://docs.github.com/en/github/writing-on-github) For a hands-on guide to customizing your profile README, see ["Quickstart for Writing on GitHub."](https://docs.github.com/en/github/writing-on-github)

## Prerequisites
GitHub will display your profile README on your profile page if all of the following are true:

- You've created a repository with a name that matches your GitHub username.
- The repository is public.
- The repository contains a file named `README.md` in its root.
- The `README.md` file contains any content.

**Note:** If you created a public repository with the same name as your username before July 2020, GitHub won't automatically show the repository's README on your profile. You can manually share the repository's README to your profile by going to the repository on GitHub and clicking "Share to Profile."

## Adding a Profile README
1. In the upper-right corner of any page, select the `+` icon, then click **New Repository**.

   ![GitHub Dropdown Menu](https://github.githubassets.com/images/modules/site/new-repo.png)

2. Under "Repository name," type a repository name that matches your GitHub username. For example, if your username is "octocat," the repository name must be "octocat."
3. Optionally, in the "Description" field, type a description of your repository. For example, "My personal repository."
4. Select **Public**.
5. Select **Initialize this repository with a README**.
6. Click **Create Repository**.
7. Above the right sidebar, click **Edit README**.

The generated README file is pre-populated with a template to give you some inspiration for your profile README.

For a summary of all the available emojis and their codes, see ["Emoji Cheat Sheet."](https://emojipedia.org/)

## Removing a Profile README
The profile README will be removed from your GitHub profile if any of the following apply:

- The README file is removed or made empty.
- The repository is made private.
- The repository name no longer matches your username due to a change in either or both names.

The method you choose depends upon your needs, but if you're unsure, we recommend making your repository private. For steps on how to make your repository private, see ["Setting Repository Visibility."](https://docs.github.com/en/github/administering-a-repository/changing-a-repositorys-visibility)

---

# Quickstart for Repositories

Learn how to create a new repository and commit your first change in 5 minutes.

## Tool Navigation
- **GitHub CLI**
- **Web Browser**

## In This Article
- Create a Repository
- Commit Your First Change
- Next Steps

## Create a Repository
GitHub repositories store a variety of projects. In this guide, you will create a repository and make your first change.

1. In the upper-right corner of any page, select the `+` icon, then click **New repository**.

   ![GitHub Menu](https://github.githubassets.com/images/modules/site/new-repo.png)

2. Type a short, memorable name for your repository. For example, "hello-world".

   ![Repository Name](https://github.githubassets.com/images/modules/repository/new-repository.png)

3. Optionally, add a description of your repository. For example, "My first repository on GitHub."

4. Choose a repository visibility. For more information, see "About repositories."

5. Select **Initialize this repository with a README**.

6. Click **Create repository**.

Congratulations! You've successfully created your first repository and initialized it with a README file.

### Analogy
Creating a repository on GitHub is like opening a **new folder** on your computer. By naming the folder and adding a README, you’re giving purpose and context to the files it will contain, much like an organizer.

## Commit Your First Change
A commit is like a **snapshot** of all the files in your project at a particular point in time.

When you created your new repository, you initialized it with a README file. README files are a great place to describe your project in more detail or add documentation, such as how to install or use your project. The contents of your README file are automatically shown on the front page of your repository.

Let’s make a change to the README file.

1. In your repository's list of files, select `README.md`.

   ![File List](https://github.githubassets.com/images/modules/repository/readme-file-list.png)

2. In the upper right corner of the file view, click the pencil icon to open the file editor.

   ![File Editor](https://github.githubassets.com/images/modules/repository/edit-file.png)

3. In the text box, type some information about yourself.

4. Above the new content, click **Preview**.

   ![Preview](https://github.githubassets.com/images/modules/repository/preview-file.png)

5. Review the changes you made to the file. If you select **Show diff**, you will see the new content in green.

   ![Show Diff](https://github.githubassets.com/images/modules/repository/preview-diff.png)

6. Click **Commit changes...**

7. In the "Commit message" field, type a short, meaningful commit message that describes the change you made to the file. You can attribute the commit to more than one author in the commit message. For more information, see "Creating a commit with multiple authors."

8. Below the commit message fields, decide whether to add your commit to the current branch or to a new branch. If your current branch is the default branch, you should choose to create a new branch for your commit and then create a pull request. For more information, see "Creating a pull request."

   ![Pull Request](https://github.githubassets.com/images/modules/repository/pull-request-options.png)

9. Click **Commit changes** or **Propose changes**.

### Analogy
Making a commit is like **taking a photo** of your progress on a project. By capturing the current state of your README, you can return to that "photo" in the future if you need to remember how things were before the changes.

## About Repository Visibility
You can restrict who has access to a repository by choosing a repository's visibility: public or private.

When you create a repository, you can choose to make it public or private. Repositories in organizations that use GitHub Enterprise Cloud and are owned by an enterprise account can also be created with internal visibility. For more information, see the GitHub Enterprise Cloud documentation.

- **Public repositories** are accessible to everyone on the internet.
- **Private repositories** are only accessible to you, people you explicitly share access with, and, for organization repositories, certain organization members.

Organization owners always have access to every repository created in an organization. For more information, see "Repository roles for an organization."

People with admin permissions for a repository can change an existing repository's visibility. For more information, see "Setting repository visibility."