# Commit Messages

## Fundamentals Course

### Introduction
This lesson will explain the importance of good commit messages, how to write them, when to commit, and why having a history of good commits is so important.

### Lesson Overview
This section contains a general summary of the topics you will learn in this lesson.

1. How to write a meaningful commit message.
2. Why meaningful commit messages are important.
3. When to make a commit.
4. Are commit messages so important that they deserve their own lesson?
   - Yes! Here’s a quick list of reasons why:

   - When applying for jobs, employers will review your projects on GitHub and examine your commit history. Having good commits as a novice developer will help you stand out.
   
   - A good history of commit messages will allow you (or other developers working on your code) to quickly see what changes were made and why. This is useful if a bug is found in the code that needs fixing!
   
   - A good history of commit messages will also be helpful if you return to a project you were working on after a while. You probably won’t remember your thought process and the changes made when you originally wrote the code.

### Bad vs. Good Commits
When writing commits, it's crucial to know how to write them effectively. Here’s an example of a bad commit message:

```
fix a bug
```
While it describes what you did, the message is too vague, leaving other developers on your team confused. A good commit message will explain the **why** behind your changes. In other words, a commit message describes what problem your changes solve and how they do it.

Effective commits consist of two parts: a **subject** and a **body**.

#### Subject
A brief summary of the change you made to the project.  
Example: 
```
Add missing link and alt text to company logo
```
GitHub has a limit of 72 characters, so we recommend keeping the subjects of your commits within that amount.

#### Body
A concise but clear description of what you did.  
Example:
```
Screen readers will not read images to users with disabilities without this information.
```
Ah, that's better! Now, developers can better understand this commit message because:

- It provides a subject that specifies the action of your code (e.g., “Add missing link and alt text to company logo”).
- It contains a body that provides a concise but clear description of why it was necessary to make the commit (e.g., “Screen readers will not read images to users with disabilities without this information”).
- It separates the subject from the body with a blank new line. This is a recommended practice that we advise following. It makes commit messages easier to read for other developers.

### How to Make a Commit with a Subject and Body in the Message
So far, you have been told to make a commit with `git commit -m <message>`. To make a commit with a subject and a body in the message, the simplest way is to type `git commit` without the `-m` option and the message argument.

This will open a new tab in Visual Studio Code if you have set it as your Git editor. You can delete any comments and write your messages in multiple lines. When you save and close the tab, your commit will be created.

### When to Make a Commit
A good way to view a commit is as a “snapshot” of your code at the moment it was made. That version of your code up to that point will be saved so you can return to it or look back at it later.

When writing code, it is considered good practice to make a commit each time you have a significant change in the code. This will create a timeline of your progress and show that your final code didn’t appear out of nowhere.

In other words, make a commit if you manage to get a piece of code working as you want, fix a typo, or correct a bug. As you gain experience, you will develop a better perception of what should be committed.

There will come a time when you are working on a project and finally get something just the way you wanted it (this would be a good time to make a commit!), and maybe 30 seconds to a few days later, it breaks. You have no idea what you changed, everything seems to be the same, and you don’t remember editing that line, but unfortunately, it no longer works as you wanted. You could check your commit history and revert your code to the last commit you made when that part was working, or go back and see how your code looked at that time.

### Assignment
This article, [How to Write a Commit Message in Git](https://example.com), covers all the main aspects of how to write good commit messages. The full article is excellent and informative, but the most important part is “The Seven Rules for a Great Commit Message.”

### Tips and Things to Remember
- Using VSCode as your text editor (you should have set it up in the Git Fundamentals section) will allow you to easily create multi-line commit messages, see the character length of each line, and use spell-check extensions in VSCode to ensure your spelling is correct.
- Use active voice: “Fix card generator.”
- Avoid vague commit messages like “saved” or “updated.”
- Commit early and often!

### Knowledge Review
The following questions are an opportunity to reflect on key themes in this lesson. If you can’t answer a question, click on it to review the material, but keep in mind that you’re not expected to memorize or master this knowledge.

1. What are two benefits of having well-written commit messages and a good commit history?
2. How many characters should the subject line of your commit message have?

### Additional Resources
This section contains useful links to related content. It is not mandatory, so consider it supplemental.

- One way to formulate commit messages with lots of information is to follow a template. [Conventional Commits](https://example.com) is one of the many commit message templates you can explore.
- Check out this amazing video tutorial on [Conventional Commits](https://example.com). The video shows the Conventional Commits template from the previous resource. It also mentions versioning and demonstrates the use of something called “Yarn.” These two parts are outside the scope of this part of the course, so don’t worry about them and focus on the commit template.

---

## What Exactly is a Commit Message?
A commit message is a descriptive text that is added by the developer who made the commit to the commit object.

### Why Should You Write Good Commit Messages?
There are several uses for commit messages:

- Future readers will have no trouble understanding what changed and why it changed.
- Facilitate undoing certain modifications.
- Make changes to the release notes.

Each of these use cases requires a consistent commit message style.

### Commit Options
- `-m` (to add the commit message)  
  ```bash
  git commit -m "your commit message here"
  ```
- `-a` or `--all` (adds and commits tracked files with a single command)  
  ```bash
  git commit -a -m "your commit message here"
  ```
- `--amend` (allows you to modify and add changes to the most recent commit)  
  ```bash
  git commit --amend
  ```
**Note:** It’s excellent to use `--amend` to clean up local commits, and once you’re done, you can push the updated version to a shared repository. However, it’s better to avoid changing commits that have already been made public.

### How to Write Good Commit Messages
Here’s a great template for a good commit message.

```
[optional Ticket-Id] <type>[optional scope]: <description>

[optional body]
```
Examples:
```
(JIRA-231) feat (dashboard): add logout button
```
or
```
build: update version
```
or
```
(JIRA-333) fix (profile): test commit
```

### IMPORTANT Change
To show how to add a body in the commit, the commit type can be:
- `feat:` Commits that add a new feature.
- `fix:` Commits that fix a bug.
- `refactor:` Commits that rewrite/restructure your code without changing any behavior.
- `perf:` Commits that are special refactoring commits that improve performance.
- `style:` Commits that do not affect meaning (whitespace, formatting, missing semicolons, etc.).
- `test:` Commits that add missing tests or fix existing tests.
- `chore:` Commits that do not affect behavior or are not important parts of the project.

### Rules for Good Commit Messages
- The imperative should be used.
- The message should be brief but descriptive; the first block should be a maximum of 50 characters.
- A blank line should separate the summary from the body.
- The body should have a maximum of 72 characters per line.

---

# Roadmap to Frontend Development: Git Branch Naming and Pull Request Best Practices

## Naming Conventions for Git Branches — a Cheatsheet

Git is like a time machine for your code, allowing developers to track changes and collaborate effectively. One essential aspect of using Git is the naming of branches. A branch is essentially a unique set of code changes that comes with its own name.

### The Importance of Branch Naming

Think of branches as different paths in a garden. Just as clear paths help you navigate the garden, descriptive branch names help you and your team understand what each branch is about. Here are some best practices to keep your garden neat and navigable:

### Basic Rules

1. **Lowercase and Hyphen-separated**: Use lowercase letters for branch names, with words separated by hyphens. For example, `feature/new-login` or `bugfix/header-styling`. 
   
   - **Analogy**: Imagine writing a recipe. Each ingredient should be clearly labeled to avoid confusion.

2. **Alphanumeric Characters**: Stick to alphanumeric characters (a-z, 0–9) and hyphens. Avoid punctuation, spaces, underscores, or any non-alphanumeric character.

   - **Analogy**: Just like a simple password is easier to remember, simpler branch names are easier to handle.

3. **No Continuous Hyphens**: Avoid using continuous hyphens. For example, `feature--new-login` can be confusing.

   - **Analogy**: Think of a train track; too many tracks can lead to confusion and derailment.

4. **No Trailing Hyphens**: Don’t end branch names with a hyphen. For instance, `feature-new-login-` is not advisable.

5. **Descriptive**: The name should be concise yet descriptive, reflecting the work done in the branch.

### Branch Prefixes

Using prefixes in branch names helps quickly identify their purpose. Here are some common prefixes:

- **Feature Branches**: Used for developing new features. Prefix: `feature/`. Example: `feature/login-system`.
  
  - **Analogy**: This is like adding new flavors to your ice cream menu.

- **Bugfix Branches**: Used to fix bugs in the code. Prefix: `bugfix/`. Example: `bugfix/header-styling`.

  - **Analogy**: It’s like patching a hole in your favorite shirt.

- **Hotfix Branches**: Created directly from the production branch to fix critical bugs. Prefix: `hotfix/`. Example: `hotfix/critical-security-issue`.

  - **Analogy**: This is like putting out a fire in your kitchen—urgent and necessary!

- **Release Branches**: Used to prepare for a new production release. Prefix: `release/`. Example: `release/v1.0.1`.

  - **Analogy**: Think of it as the final check before a big event.

- **Documentation Branches**: For writing or updating documentation. Prefix: `docs/`. Example: `docs/api-endpoints`.

### Including Ticket Numbers

In larger teams, including a ticket number from a project management tool (like Jira) in the branch name is common. This makes it easy to track work. For example, if working on a ticket numbered “T-123” for a new login system, the branch name could be `feature/T-123-new-login-system`.

### Sample Branch Names

Here are some good examples of branch names that follow these conventions:

- `feature/T-456-user-authentication`
- `bugfix/T-789-fix-header-styling`
- `hotfix/T-321-security-patch`
- `release/v2.0.1`
- `docs/T-654-update-readme`

### Conclusion

While Git doesn't enforce branch naming conventions, following them is crucial for maintaining a clean and understandable codebase, especially in team environments. By adopting these practices, your workflow can become significantly more efficient.

---

## Best Practices for Pull Requests

Pull requests (PRs) are essential for maintaining the quality of the codebase. Think of a PR as an invitation to your housewarming party; you want to ensure everything is in order before the guests arrive.

### Best Practices for Creating Pull Requests

1. **Write Small PRs**: Aim to create small, focused pull requests that fulfill a single purpose.

   - **Analogy**: It's like preparing individual dishes for a multi-course meal; each dish should shine on its own.

2. **Review Your Own Pull Request First**: Before submitting, review, build, and test your PR to catch any mistakes.

   - **Analogy**: Just like proofreading a letter before sending it, this helps ensure clarity and correctness.

3. **Provide Context and Guidance**: Write clear titles and descriptions for your pull requests to help reviewers quickly understand the changes.

   - **Analogy**: Think of it as giving directions to your guests on how to reach your home; clear instructions help avoid confusion.

4. **Share the Type of Feedback Needed**: Indicate whether you need a quick look or a detailed critique.

   - **Analogy**: Just as you might ask for feedback on your home decoration, specify what you want to improve.

5. **Guide Reviewers on File Review Order**: If changes span multiple files, provide guidance on the review order.

   - **Analogy**: It’s like giving your guests a tour of your house, highlighting the important rooms first.

### Best Practices for Managing Pull Requests

1. **Use Pull Request Templates**: Create templates to standardize the information required in PRs.

   - **Analogy**: Similar to having a checklist for planning a party, templates help maintain consistency.

2. **Define Code Owners**: Specify individuals responsible for reviewing changes to certain files or code.

   - **Analogy**: It’s like assigning roles for party preparations; everyone has their responsibilities.

3. **Use Protected Branches**: Prevent merging into important branches until certain conditions are met.

   - **Analogy**: Think of it as a bouncer at a club ensuring that guests meet entry requirements.

4. **Use Push Rulesets**: Block pushes based on file extensions, path lengths, or sizes to maintain quality.

   - **Analogy**: It’s like having rules for attire at your party; not everything is welcome.

5. **Use Automated Tools for Code Styling**: Employ tools like linters to maintain consistent styling.

   - **Analogy**: Similar to hiring a decorator to ensure everything looks good at your party, these tools help maintain code quality.

### Conclusion

By following these best practices for pull requests, you can improve collaboration and maintain the integrity of the codebase. Think of it as hosting a well-organized party where everything flows smoothly and everyone has a good time!

---

# A Practical Guide for Better, Faster Code Reviews

"A code review is a dialogue, but it is also a critique of a person’s work, and both reviewer and author should bear in mind the psychology of ownership and criticism. Some of the most valuable things that come up during code review are things which different developers can reasonably disagree about, and discussing such things is exactly how we learn and innovate." 
— Alexandra Hill, *The Art of Giving and Receiving Code Reviews (Gracefully)*

## Disclaimer
All the information provided has been compiled & adapted from the references cited at the end of the document. The guidelines are illustrated by my own examples, fruit of my personal experience writing and reviewing code. Many thanks to all of the sources of information & contributors.

---

## 📔 Considerations

A code review is a dialogue, and as such, it should always be done in a respectful and constructive way.

Many programming decisions are opinions. A code review opens a conversation about trade-offs in order to reach a resolution that everyone is satisfied with.

A code review is a form of asynchronous communication, so a lot of context (like body language and the opportunity for back-and-forth) is lost.

For both authors and reviewers, a code review is a collaborative tool for knowledge spreading and for code quality improvement.

---

## 📔 Guidelines

### For Both Authors and Reviewers

#### Be Respectful / Ask - Explain - Suggest
Always be considerate and respectful, specifically:

- **Don't** use the imperative
- **Don't** judge
- **Don't** blame (don't even think about cursing)
- **Don't** be arrogant
- **Don't** use sarcasm.

Instead:

- **Ask** questions, assuming that everyone is intelligent and well-meaning
- **Explain** your point of view in an explicit manner, even if it's a bit more verbose
- **Suggest** improvements.

**Analogy**: Think of a code review like a cooking class where everyone is learning. If someone’s dish doesn’t turn out well, you wouldn’t say, "This is wrong!" Instead, you’d ask, "What ingredients did you use?" and suggest ways to improve the flavor.

---

#### Stop the "Reply" Hemorrhage / Offer to Talk in Person
Many replies to a comment might be the symptom of miscommunication, misunderstanding, or lack of knowledge. They can create a lot of noise for everyone participating in the review, as well as frustration.

Should it be the case, offer to talk in person to clarify the topic under discussion, to agree on a solution and/or to pair on any changes suggested.

Once done, post a concise comment to summarize the conversation and to share the agreement with everyone.

**Analogy**: Imagine trying to fix a broken toy over text messages. It’s much easier to sit down together and figure out how to fix it face-to-face rather than going back and forth with unclear instructions.

---

#### Offer Encouragement & Appreciation / Give Positive Feedback
Code reviews often just focus on mistakes, but they should also offer encouragement and appreciation for good practices.

Whether you learned something thanks to a comment written by one of your peers, or when you read an elegant piece of code, or even just to congratulate the good work, say: "Thank you!", "Great!", "Nice!".

It makes a huge difference to receive positive feedback!

**Analogy**: Like a teacher praising a student for a job well done, positive feedback in code reviews encourages developers and motivates them to keep improving.

---

#### Agree on a Coding Style / Automate
Conversations about coding style are often long and unproductive. After all, it's a matter of personal taste, and everyone has their own preference.

This is why it's important to find a coding style that your team can adhere to and to use automation tools to ensure that it is being followed (code formatters, linters). By removing personal tastes from the review, everyone can focus on what's most important: code quality and best practices.

**Analogy**: Imagine a sports team where every player uses their own rules. To win, everyone needs to agree on the same set of rules. Similarly, a coding style guide ensures everyone on the team is "playing" the same way.

---

## 🖋️ For the Authors

### And the First Reviewer is... You! / Assess Your Code
After creating the pull request (PR) and before inviting anyone, take some time to assess your own code. Reviewing your changes outside of your IDE could help you spot inconsistencies, mistakes, missing parts, or even find easier ways to solve the problem at hand.

---

### Be Proactive / Provide Context
If the PR is complex, write a general comment to explain its purpose, give an overview of the changes being made, and share any relevant information about your choices. It will help your reviewers to dive into the review without effort, which will surely result in fewer comments and a faster review.

If there are many changes, highlight the most important parts.

**Analogy**: Think of this like giving a presentation. You wouldn’t just dive into the details without explaining what you’re presenting. Providing context makes it easier for your audience (the reviewers) to understand your main points.

---

### Wait for the Green Light
Save time for everyone: if your CI/CD pipeline has a test stage, wait until all tests have passed before inviting anyone to the review. You don't want the first comment to be "The build is failing :/".

---

### Choose Your Audience
Take some time to choose your reviewers. Prior to inviting them, ask yourself:

- Who should I give visibility of the changes being made? Who could be impacted by those changes?
- Who has time to review my code?
- Who is qualified to give me the best feedback?

**Analogy**: If you were to cook a meal, you wouldn’t ask someone who’s allergic to seafood to taste your shrimp dish. Choose the right reviewers who can provide valuable insights.

---

### Choose the Right Number of Reviewers
Be inclusive, but not too much. Having a large number of reviewers might lead to:

- Too many comments/suggestions going in too many different directions.
- Too few comments when everyone thinks someone will take care of the review.

To prevent this, you can start with a few core reviewers to receive the main feedback, then add more people to give them visibility.

---

### Keep It Small / Divide and Conquer
Small successive PRs, each one focused on a single change, will be reviewed more quickly and thoroughly.

Try to organize your work to be able to break a complex task into a succession of simpler ones. Value your reviewers' time; they will thank you, and you will benefit from faster and more valuable feedback.

**Analogy**: It’s like cleaning your room. Instead of tackling everything at once and getting overwhelmed, you focus on one corner at a time, making the process easier and more manageable.

---

### Rome Wasn't Built in a Day / Create New Tasks
If the need for a big refactoring or substantial changes arises during the review, create a new task and add a link to it in the review.

Remember that, the longer a review takes:

- The bigger the number of changes
- The higher the risks of merge conflicts
- The greater the probability of demotivating everyone involved in the review.

---

### Don't Take It Personally / Keep an Open Mind
One of the goals of a code review is to maintain the quality of the code base. When a reviewer provides a critique of your code, think of it as their attempt to help you, rather than as a personal attack on you or your abilities.

If you feel offended, ask for explanations before reacting, take some distance, assume the best intention from the reviewer, and try to evaluate your code critically, as if someone else had written it.

Always keep in mind that it's not about you; it's about better code, a better project built with your colleagues.

---

### Clarify the Code First / Help Future Developers
If a reviewer says that they don't understand something in your code, your first response should be to clarify the code itself. If the code can't be clarified, add a code comment that explains why the code is there. If a comment seems pointless, only then should your response be an explanation in the code review.

**Analogy**: Think of it like a guidebook for tourists. If a tourist finds a place confusing, the guide should clarify the directions rather than just saying, "Figure it out!" Helping future readers understand your code is just as important.

---

### Leave This World a Little Better Than You Found It / The Boy Scout Rule
Opening a PR is a chance to improve the existing code base: have you noticed a missing test? A method that is too long? Some naming inconsistencies?

You don't have to make a big change or make the code look perfect, just a little bit better than before!

If you find a mess, try to clean it up, regardless of who might have made it. By doing this, you intentionally improve the code base for all the developers, helping the project to get better and better as it evolves.

---

### Answer All Comments / Write the End of the Story
Before closing the review, answer all the comments. Not only as a matter of respect for your reviewers (after all, they are spending time and energy as well) but also because a review is a dialogue, and as such, it should have a clear conclusion.

Moreover, it can be helpful as a reference in the future.

---

### Practice Mindfulness / Love
Take a few deep breaths... Repeat a mantra that is focused on gratitude and kind speech, for instance:

*Code can travel thousands of miles and affect many people.*

*I vow to write code mindfully and lovingly.*

*May this code create mutual understanding and peace.*

Find your own mantras and spread the love!

---

## 👀 For the Reviewers

### You Are Not the Boss of Them / Act Like a Mentor
Just like a teacher is not just there to correct mistakes, you are not there to dictate how things should be. Rather, you’re a mentor here to share knowledge and best practices to help others grow.

### Be Open-Minded
You might not agree with everything the author has done. Always keep in mind that they have their own point of view and reasoning. Be open-minded to alternatives and try to share your point of view in a constructive manner.

---

### Keep It Focused / Avoid Bikeshedding
When reviewing code, focus on important things and try to avoid minor issues, especially when they are based on personal taste. Make sure that what you're commenting on is in line with the overall goal of the review.

In case you have a suggestion about something minor that does not impact code quality, leave it out and instead offer it as a piece of advice or feedback during an informal conversation or as a follow-up task.

**Analogy**: It’s like when you go to a restaurant. If the main dish is excellent, you might overlook a small issue with the garnish. Focus on what truly matters first.

---

### Spread the Joy! / Give a Heart
You may have the chance to highlight some of the best parts of the code being reviewed, be it a clean and clever solution, or just a simple and effective approach. This will reinforce good practices and encourage the author to keep writing great code in the future!

---

## 🏁 Conclusion
As long as we continue improving our code through healthy code reviews, our software will keep evolving. And as our software improves, so does our work environment. 

---

# Understanding Code Reviews and Contribution Guidelines

## Introduction
As we embark on the journey to becoming proficient frontend developers, one essential aspect we must grasp is the significance of code reviews and how to set effective contribution guidelines. This article explains the importance of these practices and provides analogies to clarify the concepts.

---

## Code Reviews: The Quality Control of Code

### What is a Code Review?
Imagine a chef preparing a gourmet dish. Before serving it to customers, the dish undergoes a tasting by another chef to ensure it meets quality standards. Similarly, a **code review** is a process where one or more developers evaluate the code written by another developer. The aim is to ensure that the code is ready to be merged into the main codebase.

### Why Are Code Reviews Important?
Code reviews serve several vital purposes:

- **Quality Assurance:** Just as a chef checks for flavor and presentation, code reviewers check for bugs and adherence to coding standards. They ensure the code is not only functional but also maintainable.
  
- **Knowledge Sharing:** Consider code reviews as a cooking class where chefs share their secrets and techniques. Developers learn from each other, fostering a collaborative environment.

- **Error Detection:** Detecting errors early in the coding process saves time and resources, much like spotting a burnt dish before it leaves the kitchen.

### Benefits of Code Reviews
1. **Increase Code Quality:** By identifying defects, much like a second opinion in medicine, the final product becomes robust and reliable.
  
2. **Compliance with Standards:** Code reviews ensure that the dish (code) adheres to the restaurant's (organization’s) recipe (coding standards).

3. **Cost-Efficiency:** Catching issues early is cheaper than fixing them later. It's like preventing a kitchen fire instead of dealing with the aftermath.

4. **Boost Collaboration:** Code reviews provide a platform for developers to discuss ideas and best practices, similar to how chefs exchange recipes and cooking tips.

### Challenges in Code Reviews
While beneficial, code reviews can also pose challenges:

- **Time-Consuming:** Reviewing large codebases can be as lengthy as preparing a complicated dish.
  
- **Subjectivity:** Different reviewers might have varying opinions, akin to chefs arguing about the best seasoning for a dish.

- **Costly:** Manual code reviews can be labor-intensive, making them expensive for smaller teams, similar to high operational costs in a restaurant.

### The Code Review Process
1. **Preparing Code:** The author ensures the code is complete and well-documented, just as a chef would prep ingredients before cooking.

2. **Requesting Reviews:** The code author submits the code for review, much like a chef presenting their dish to a panel of judges.

3. **Reviewing Code:** Reviewers examine the code, point out issues, and suggest improvements—similar to chefs critiquing each other's dishes.

4. **Discussing Comments:** Developers discuss comments left by reviewers, negotiating adjustments like chefs discussing alterations to a recipe.

5. **Approving Code:** Once all issues are resolved, the code is approved and merged, akin to a dish being deemed ready for serving.

### Types of Code Reviews
- **Formal Code Reviews:** In-depth evaluations resembling a culinary competition where every detail is scrutinized.

- **Over-the-Shoulder Reviews:** Real-time collaborative reviews, much like chefs working side by side in the kitchen.

- **Asynchronous Reviews:** Reviews done independently, ideal for remote teams, akin to chefs preparing dishes in their own kitchens.

- **Tool-Assisted Reviews:** Using tools to streamline the process, similar to employing kitchen gadgets for efficiency.

### Code Review Tools
Various tools aid in the code review process, such as:
- **Pull Requests:** Like a menu proposal where chefs suggest new dishes for the restaurant.

- **Code Discussion Tools:** Platforms for developers to leave comments and ask questions about the code, similar to chefs critiquing dishes during a tasting session.

### Enhancing Code Reviews with AI
AI-powered tools help automate and accelerate the review process, identifying issues more quickly—much like a high-tech oven that alerts chefs if something is burning.

---

## Setting Guidelines for Repository Contributors

### Why Are Contribution Guidelines Important?
Just as restaurants have recipes to ensure consistent quality, contribution guidelines help contributors understand how to interact with the project. They save time by minimizing poorly formed pull requests or issues that need to be rejected and resubmitted.

### Adding a CONTRIBUTING File
To create contribution guidelines:
1. Navigate to your repository on GitHub.
2. Click on **Add file**, then **Create new file**.
3. Name the file `CONTRIBUTING.md`.

### What to Include in Contribution Guidelines
- **Steps for Creating Good Issues or Pull Requests:** Outline what makes an issue or pull request effective—much like a recipe detailing necessary ingredients.

- **Links to Documentation:** Provide helpful resources to guide contributors, similar to a cookbook with additional references.

- **Community Expectations:** Set behavioral standards, ensuring a respectful and collaborative atmosphere, just as chefs maintain professionalism in the kitchen.

### Examples of Contribution Guidelines
If you're unsure how to structure your guidelines, check out:
- [GitHub Docs Contribution Guidelines](https://github.com/github/docs/blob/main/CONTRIBUTING.md)
- [Ruby on Rails Contribution Guidelines](https://github.com/rails/rails/blob/main/CONTRIBUTING.md)
- [Open Government Contribution Guidelines](https://github.com/opengov/guide/blob/master/CONTRIBUTING.md)

---

## Conclusion
By understanding the importance of code reviews and establishing clear contribution guidelines, we set ourselves up for success in our journey to becoming proficient frontend developers. Much like a well-run kitchen, where every dish is carefully crafted and evaluated, these practices ensure that our code is of the highest quality and our team functions smoothly.

---

# Contributing Guidelines

Oftentimes, open source projects place a `CONTRIBUTING` file in the root directory. It explains how participants should do things like format code, test fixes, and submit patches. Here is a fine example from Puppet and another one from Factory Girl Rails. From a maintainer’s point of view, the document succinctly communicates how best to collaborate. And for a contributor, one quick check of this file verifies their submission follows the maintainer’s guidelines.

### Contributors Wanted: Inquire Within

Today, we added support for sharing your preferred policy for contributions with those wanting to collaborate with you on your project. We’ve tried making this easy for everyone. As a maintainer, all you have to do is add a `CONTRIBUTING` file (or `CONTRIBUTING.md` if you’re using Markdown) to the root of your repository. Then we will add a link to your file when a contributor creates an Issue or opens a Pull Request.

Now, as soon as your collaborators start participating, they can easily find the guidelines you’d like them to follow. If you don’t see a `CONTRIBUTING` file in your favorite project, open a pull request and add one.

## Do You Have a Readable GIT Commit History?

It might seem like there are few reasons to care about your Git history. It seemed the same to me when I first had to start caring about it, because someone made me do it 🤓. 

As with everything, there will be a point where you need to have a clear understanding of your own and your team’s changes, their succession, and have to find something meaningful from all this information — either when did a particular file get changed, which version included what changes, who did which change in what order.

### Why Should You Care About Your Git History Being as Readable as Possible?

Imagine trying to read a book with jumbled pages; you wouldn't be able to follow the story. A clear commit history is like a well-ordered book. It allows you to:

- **Easily decipher the order of the commits** in your repository.
- **Understand more easily what and when was changed.**
- **Facilitate finding commits** that might have introduced bugs and enable rollback if necessary.
- **Automatically extract release notes** and create a changelog.
- **Deploy any commit** on your development branch using your CI/CD system.
- **Identify features in specific releases** for mobile app releases.

### Steps to Get a Clean Commit History

1. **Understand rebase:** Instead of pulling changes from a remote branch, rebase your working branch to keep your history clean and linear.
   ```bash
   git fetch
   git rebase origin/shared_branch
   ```

2. **Use fast-forward or squash merging:** This helps maintain a clean history when merging changes into the target branch.
   ```bash
   git merge --squash working_branch
   git commit -m "Squashed commit from working_branch"
   ```

3. **Make atomic commits:** Learn how to amend, squash, or restructure your commits to keep them meaningful.
   ```bash
   git commit --amend
   ```

4. **Force push with caution:** After rebasing or amending commits, you'll often need to force push your changes to the remote repository.
   ```bash
   git push -f
   ```

### Rebasing Your Working Branch

You already have a few commits, but an important change has been made on the shared branch that you need to continue your work. You have two options:

- **Merge the shared branch into yours**, which will result in a merge commit. This makes the history cluttered and can lead to confusion later.
  ```bash
  git merge origin/shared_branch
  ```

- **Rebase your commits on top of the remote branch.** This applies your commits one by one on top of the latest commit from the shared branch, keeping the history linear.
  ```bash
  git rebase origin/shared_branch
  ```

If conflicts arise during the rebase, resolve them and then continue with:
```bash
git rebase --continue
```
If needed, you can abort the rebase with:
```bash
git rebase --abort
```

If your local branch was already pushed to remote, you will need to force push after the rebase. Be careful with this, as it will overwrite the remote state.

### Rearranging and Changing Your Commits

If you need to make small changes to previous commits, like correcting typos or reordering commits for clarity, you can use an interactive rebase:
```bash
git rebase --interactive origin/target_branch
```

This allows you to modify your commit history easily. Just remember that these operations should only happen before you create a Pull Request, not on the shared branch.

### Generating a Changelog from Your Commit History

Using basic Git commands, you can format your commit messages to generate a meaningful changelog, reflecting the importance of your commit messages in the first place. This could involve using tools like Fastlane to automate the process further.

By following these guidelines and practices, you'll contribute to a cleaner, more understandable project that benefits both contributors and maintainers.

---

## About CITATION Files

Imagine you are a librarian. You want to help people find the right books for their research. A CITATION file in a repository acts like a library card that guides users on how to properly cite your software. This way, anyone using your work knows exactly how to give you credit, just like how a good librarian makes sure each book has its proper card.

### What is a CITATION file?

A CITATION.cff file can be added to the root of your repository. This file contains information about how you would like others to cite your work, in a format that's easy for both humans and machines to read. It’s like providing a detailed label for each book on a shelf.

### Example of a CITATION.cff file:

```plaintext
cff-version: 1.2.0
message: "If you use this software, please cite it as below."
authors:
- family-names: "Lisa"
  given-names: "Mona"
  orcid: "https://orcid.org/0000-0000-0000-0000"
- family-names: "Bot"
  given-names: "Hew"
  orcid: "https://orcid.org/0000-0000-0000-0000"
title: "My Research Software"
version: 2.0.4
doi: 10.5281/zenodo.1234
date-released: 2017-12-18
url: "https://github.com/github-linguist/linguist"
```

When you include a CITATION.cff file, GitHub automatically adds a "Cite this repository" link to your repository's landing page. This makes it easy for users to find the information they need, much like a librarian pointing out the citation section.

### Citing Other Resources

Sometimes, your work isn't just about software; it could include research articles or datasets. You can use the `preferred-citation` option in the CITATION file to direct users to these resources. Think of it as adding a "Recommended Reading" section to your library card.

### Example of Citing a Research Article:

```plaintext
preferred-citation:
  type: article
  authors:
  - family-names: "Lisa"
    given-names: "Mona"
    orcid: "https://orcid.org/0000-0000-0000-0000"
  doi: "10.0000/00000"
  journal: "Journal Title"
  title: "My awesome research software"
  volume: 1
  year: 2021
```

## About Wikis

Now, think of a wiki as a community bulletin board in a library. It allows you to post and share information about your project, and anyone can contribute. Wikis can house detailed documentation, tutorials, or even FAQs about your project, making it easier for others to use and understand.

### Who Can Use Wikis?

Wikis are available in public repositories and various GitHub plans, enabling users to create and manage their project documentation. Just as anyone can post a note on a bulletin board, users can edit wikis to keep information current.

### Using Markdown in Wikis

You can write content in Markdown, which is like using a special pen that helps your notes stand out. With Markdown, you can add formatted text, images, and even mathematical expressions to your wiki, making it a versatile tool for documentation.

## About READMEs

A README file serves as the welcome mat of your project. It’s often the first thing visitors see when they arrive at your repository, much like the front desk of a library where you get information on where to find what you need.

### What Should a README Include?

Your README should clearly communicate:

- What the project does
- Why it is useful
- How to get started
- Where to find help
- Who maintains it

### Auto-Generated Table of Contents

When you write a README, GitHub generates a table of contents automatically based on section headings. This helps users navigate through your project, just like a library index helps you find books on a specific topic.

### Linking and Navigation in README

You can create relative links to other files within your repository, which is similar to referencing related books on the library shelf. This enhances user navigation and helps them explore your project more effectively.

---

# Basic Writing and Formatting Syntax on GitHub

Create a sophisticated format for your prose and code on GitHub with simple syntax.

## Headings
To create a heading, add one to six `#` symbols before your heading text. The number of `#` you use will determine the hierarchy level and the font size of the heading.

```markdown
# Level 1 Heading
## Level 2 Heading
### Level 3 Heading
```

When you use two or more headings, GitHub automatically generates a table of contents that you can access by clicking on the icon inside the header of the file. Each header title will be listed in the table of contents, and you can click on a title to navigate to the selected section.

## Styling Text
You can indicate emphasis with text in **bold**, _italic_, ~~strikethrough~~, subscript, or superscript in comment fields and `.md` files.

| Style                    | Syntax               | Example                      | Output                           |
|--------------------------|----------------------|------------------------------|----------------------------------|
| Bold                     | `** **` or `__ __`   | `**This is bold text**`     | **This is bold text**            |
| Italic                   | `* *` or `_ _`       | `_This text is italic_`     | _This text is italic_            |
| Strikethrough            | `~~ ~~`              | `~~This was an error~~`     | ~~This was an error~~            |
| Nested bold and italic    | `** **` and `_ _`    | `**This text is _extremely_ important**` | **This text is _extremely_ important** |
| All bold and italic      | `*** ***`            | `***All this text is important***` | ***All this text is important*** |
| Subscript                | `<sub> </sub>`       | `This is a <sub>subscript</sub>` | This is a subscript             |
| Superscript              | `<sup> </sup>`       | `This is a <sup>superscript</sup>` | This is a superscript           |

## Quoting Text
You can quote text with `>`.

```markdown
This is not a quote

> This is a quote
```

Quoted text is indented with a different type color.

## Quoting Code
You can mention a code or command within a sentence with backticks. The text within the backticks will not be formatted.

```markdown
Use `git status` to list all new or modified files that haven't been committed yet.
```

To format a block of code or text in its own distinct block, use three backticks.

```markdown
Some basic Git commands are:
```
```
git status
git add
git commit
```

## Supported Color Models
In issues, pull requests, and discussions, you can mention colors within a sentence using backticks. A supported color model within backticks will display a visualization of the color.

```markdown
The background color is `#ffffff` for light mode and `#000000` for dark mode.
```

Here are the currently supported color models.

| Color | Syntax         | Example                  | Output                          |
|-------|----------------|--------------------------|---------------------------------|
| HEX   | `#RRGGBB`      | `#0969DA`                | ![#0969DA](https://via.placeholder.com/15/0969DA/000000?text=+) |
| RGB   | `rgb(R,G,B)`   | `rgb(9, 105, 218)`      | ![rgb(9,105,218)](https://via.placeholder.com/15/0969DA/000000?text=+) |
| HSL   | `hsl(H,S,L)`   | `hsl(212, 92%, 45%)`    | ![hsl(212,92%,45%)](https://via.placeholder.com/15/0969DA/000000?text=+) |

## Links
You can create a link in-line by wrapping the link text in `[ ]`, then wrapping the URL in `( )`.

```markdown
This site was built using [GitHub Pages](https://pages.github.com/).
```

## Section Links
You can directly link to any section that has a heading. To see the automatically generated anchor in a rendered file, hover over the section heading to expose the icon and click the icon to show the anchor in your browser.

```markdown
[Link to sample heading](#sample-heading).
```

## Relative Links
You can define relative links and image paths in your rendered files to help readers navigate to other files in your repository.

```markdown
[Contribution guidelines for this project](docs/CONTRIBUTING.md)
```

## Custom Anchors
You can use standard HTML anchor tags (`<a name="unique-anchor-name"></a>`) to create navigation anchor points for any location in the document.

```markdown
# Section Header

<a name="my-custom-anchor"></a>
Text I want to provide a direct link to, but that doesn’t have its own header.
```

## Images
You can display an image by adding `!` and wrapping the alt text in `[ ]`. Then, wrap the link for the image in `( )`.

```markdown
![Image description](https://myoctocat.com/assets/images/base-octocat.svg)
```

## Lists
Lists can be ordered or unordered. To create an unordered list, use `*`, `+`, or `-` to start a new list item.

```markdown
- Item 1
- Item 2
  - Sub-item 2.1
  - Sub-item 2.2
```

For ordered lists, simply number the items.

```markdown
1. First item
2. Second item
   1. Sub-item 2.1
   2. Sub-item 2.2
```

## Task Lists
You can create task lists using a special syntax.

```markdown
- [ ] Task 1
- [x] Completed task
```

## Mentioning People and Teams
You can mention people or teams in comments using `@`.

```markdown
@username or @team
```

## Referencing Issues and Pull Requests
To reference an issue or pull request, use `#` followed by the number.

```markdown
Reference to issue #123.
```

## Referencing External Resources
You can include links to external resources as shown earlier.

## Uploading Assets
You can upload assets directly to your comments and Markdown files by dragging and dropping files.

## Using Emojis
You can use emojis by simply typing their code. For example, `:smile:` becomes 😀.

## Paragraphs
Paragraphs are created by leaving a blank line between blocks of text.

## Footnotes
You can add footnotes as follows:

```markdown
This is text with a footnote.[^1]

[^1]: This is the footnote.
```

## Alerts
You can use alert blocks with the following syntax:

```markdown
> **Note**: This is an important notice.
```

## Hiding Content with Comments
You can hide content by wrapping the text in `<!-- -->`.

```markdown
<!-- This content is hidden -->
```

## Ignoring Markdown Formatting
If you want text not to be processed as Markdown, use `\` before the symbol.

```markdown
\*This text is not italicized\*
```

## Disabling Markdown Rendering
To disable Markdown rendering on specific lines, use the following block:

````markdown
~~~markdown
This block will not be rendered.
~~~
````