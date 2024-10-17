# How to Collaborate in a GitHub Project

Collaborating on a GitHub project is like joining a cooking team where everyone contributes their unique recipe to create a delicious dish. Here, we will learn the steps to make your contribution effectively.

## 1. Review the Collaboration Policy in the Project

Before starting, it’s important to review the collaboration guidelines of the project. Every kitchen has its own rules, and understanding them will help you integrate better into the team.

## 2. Fork the Repository

Forking a repository is like borrowing the head chef’s recipe to modify it to your liking. In this case, we will fork the original repository:

```
https://github.com/jmsampayo/gazelle-analyser-api.git
```

To fork, go to the repository on GitHub and click the **Fork** button.

## 3. Clone the Forked Repository

Cloning the repository is like bringing your version of the recipe into your kitchen. This allows you to make changes without affecting the original recipe.

```bash
git clone https://github.com/neklaf/gazelle-analyser-api.git
```

## 4. Update the Master Branch

It's crucial to ensure that your version is up to date with the latest changes from the head chef. This is done by updating your master branch:

```bash
git pull -r upstream master
```

### Adding the Original Repository URL

First, you need to add the URL of the original repository so you can keep your version updated:

```bash
git remote add upstream https://github.com/jmsampayo/gazelle-analyser-api.git
```

### Verify the Remote Configuration

To ensure everything is in place, check the remote configurations:

```bash
git remote -v
```

You should see something like this:

```
origin	https://github.com/neklaf/gazelle-analyser-api.git (fetch)
origin	https://github.com/neklaf/gazelle-analyser-api.git (push)
upstream	https://github.com/jmsampayo/gazelle-analyser-api.git (fetch)
upstream	https://github.com/jmsampayo/gazelle-analyser-api.git (push)
```

## 5. Create a Branch for Our Improvements

Now it’s time to make our improvements. Create a new branch where you will implement your changes:

```bash
git checkout -b my-collaboration-feature
```

## 6. Make the Changes

Make the necessary modifications in your file, for example:

```bash
vim README.md
```

Check the status of your changes:

```bash
git status -s
```

You should see a result like this:

```
  M README.md
```

## 7. Commit the Changes

Now, save your changes to the history of the recipe:

```bash
git add README.md
git commit -m 'Added my awesome new feature to the project I am collaborating on'
```

## 8. Push the Changes

Now, push your changes to your forked repository on GitHub:

```bash
git push --set-upstream origin my-collaboration-feature
```

## 9. Create a Pull Request

To share your improvements with the rest of the team, you need to create a Pull Request. Be sure to link your PR with an open issue (if applicable) through the GitHub web interface.

## 10. Sync a Fork

It’s important to keep your fork in sync with the original repository. To do this, first fetch the branches and commits:

```bash
git fetch upstream
```

### Checkout Your Fork’s Local Master Branch

Make sure you are on your fork’s local master branch:

```bash
git checkout master
```

### Merge the Changes

Merge the changes from the original repository into your local branch:

```bash
git merge upstream/master
```

If your local branch doesn’t have any unique commits, Git will perform a "fast-forward":

```bash
git merge upstream/master
```

## 11. Rebase a Pull Request

If you need to rebase your Pull Request, make sure your fork is synchronized. Then, follow these steps:

1. Checkout the branch from which you originally created the PR:

    ```bash
    git checkout my-collaboration-feature
    ```

2. Run the rebase on top of your development branch:

    ```bash
    git rebase upstream/master
    ```

3. Finally, perform a **force push** to update your PR:

    ```bash
    git push -f
    ```

### What If Changes Are Required in Your PR?

It’s a best practice to have only one commit in your PR. If you made multiple commits, make sure to squash them into one:

```bash
git reset --soft HEAD~5
git commit -m "ID-1234 | Improve code quality"
```

Since you’ve already pushed changes to the remote, use:

```bash
git push origin +my-collaboration-feature
```

The `+` sign acts as a **force push** to rewrite history.

## References

- [Git Documentation](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
- [Stack Overflow on Rewriting History](http://stackoverflow.com/a/5201642/295797)
- [Combining Multiple Commits into One](https://feeding.cloud.geek.nz/posts/combining-multiple-commits-into-one/)

## Note

You can create a `git nb` alias that will facilitate creating and checking out a new branch that tracks the current branch:

```bash
git config --global alias.foo '!git checkout --track $(git config branch.$(git rev-parse --abbrev-ref HEAD).remote)/$(git rev-parse --abbrev-ref HEAD) -b'
```

## Conclusion

Collaborating on a GitHub project may seem complicated at first, but by following these steps and using these analogies, you’ll become a valuable member of the development team. Ready to cook up your next code dish!

---

### 1. Saved Replies in GitHub

**Analogy:** Think of saved replies as your pre-packed lunch for a day at work. Just like you prepare your favorite meal in advance to save time, saved replies allow you to have ready-made responses for common comments on issues or pull requests.

**Technical Concepts:**
- **Usage:** When you want to add a comment on an issue or pull request, you can quickly insert a saved reply you've set up.
- **How to Create:**
  1. Navigate to the main page of your repository on GitHub.
  2. Click on **Issues** or **Pull requests**.
  3. Choose the desired issue or pull request.
  4. Above the comment field, select the saved reply icon to insert your pre-prepared message.
  5. You can also edit the saved reply before posting it.

### 2. Mentioning Users

**Analogy:** Imagine you're in a crowded room and need to catch someone’s attention. By calling out their name, you ensure they know you need them. This is exactly how @mentions work on GitHub!

**Technical Concepts:**
- **Functionality:** When you @mention a GitHub username in a comment, that person is notified and will receive updates on that issue or pull request.
- **Managing Notifications:** You can customize your notification settings at the issue or pull request level to manage what you want to be notified about.

### 3. Adding Reactions

**Analogy:** Picture a group of friends discussing a movie. Instead of everyone shouting their opinions, they simply give a thumbs up or thumbs down to express their feelings. This keeps the conversation flowing without unnecessary noise.

**Technical Concepts:**
- **Reactions on GitHub:** You can react to pull requests, issues, and comments using emojis, helping convey your sentiments simply and effectively.
- **Purpose:** This reduces clutter in discussions while allowing users to express agreement or disagreement without lengthy comments.

### 4. GitHub Discussions

**Analogy:** Think of GitHub Discussions as a community bulletin board in a neighborhood where people can post ideas, questions, and suggestions. It's a space for open dialogue that isn't limited to specific projects or code.

**Technical Concepts:**
- **Setting Up Discussions:** 
  - Repository owners can enable GitHub Discussions for their projects.
  - This feature fosters collaborative conversations separate from code issues.
- **Creating Discussions:** Any authenticated user can start a new discussion, ask questions, or create polls to gather community input.

### 5. Organizing and Moderating Discussions

**Analogy:** Just like a well-organized library with sections for different genres, discussions on GitHub can be categorized to keep things neat and accessible.

**Technical Concepts:**
- **Creating Categories:** Repository owners can create new categories to keep discussions organized and relevant.
- **Moderation Tools:** Those with write permissions can pin important discussions, delete unhelpful ones, or convert issues into discussions for ongoing conversations.

## Conclusion

The path to becoming a frontend developer can be complex, but using analogies can simplify understanding technical concepts. By engaging with tools like GitHub, you’ll be equipped to collaborate effectively and contribute to projects in a meaningful way.

---

# Roadmap para Ser Frontend: Entendiendo GitHub

## 1. Manejo de Etiquetas

### Introducción a las Etiquetas

**Analogía:** Imagina que estás organizando una fiesta. Usas diferentes colores de cintas para clasificar los regalos: azul para los juguetes, rojo para la ropa, y verde para los libros. Las etiquetas en GitHub funcionan de manera similar, ayudando a clasificar los problemas, pull requests y discusiones de tu repositorio.

### Sobre las Etiquetas por Defecto

GitHub proporciona etiquetas predeterminadas en cada nuevo repositorio, que puedes utilizar para crear un flujo de trabajo estándar. Aquí hay algunas de las etiquetas más comunes:

| Etiqueta            | Descripción                                           |
|---------------------|------------------------------------------------------|
| `bug`               | Indica un problema inesperado o comportamiento no intencionado. |
| `documentation`     | Indica la necesidad de mejoras o adiciones en la documentación. |
| `duplicate`         | Indica problemas o solicitudes similares.            |
| `enhancement`       | Indica solicitudes de nuevas características.         |
| `good first issue`  | Indica un buen problema para contribuyentes principiantes. |
| `help wanted`       | Indica que un mantenedor desea ayuda en un problema o pull request. |
| `invalid`           | Indica que un problema, pull request o discusión ya no es relevante. |
| `question`          | Indica que se necesita más información sobre un problema, pull request o discusión. |
| `wontfix`           | Indica que no se continuará trabajando en un problema, pull request o discusión. |

### Creando una Etiqueta

Cualquiera con acceso de escritura puede crear una etiqueta. Sigue estos pasos:

1. Navega a la página principal de tu repositorio en GitHub.
2. Haz clic en **Issues** o **Pull requests**.
3. Sobre la lista de problemas o pull requests, haz clic en **Labels**.
4. Haz clic en **New label**.
5. Escribe un nombre para tu etiqueta y una descripción.
6. Opcionalmente, personaliza el color de tu etiqueta.
7. Haz clic en **Create label** para guardarla.

### Aplicando una Etiqueta

Cualquiera con acceso de triaje puede aplicar y eliminar etiquetas. Para hacerlo:

1. Navega al problema, pull request o discusión.
2. En la barra lateral derecha, haz clic en **Labels** y selecciona la etiqueta deseada.

### Editando una Etiqueta

Cualquiera con acceso de escritura puede editar etiquetas existentes:

1. Navega a la página principal del repositorio.
2. Haz clic en **Issues** o **Pull requests**.
3. Haz clic en **Labels**.
4. Al lado de la etiqueta que deseas editar, haz clic en **Edit**.
5. Realiza los cambios necesarios y haz clic en **Save changes**.

### Eliminando una Etiqueta

Cualquiera con acceso de escritura puede eliminar etiquetas existentes:

1. Navega a la página principal del repositorio.
2. Haz clic en **Issues** o **Pull requests**.
3. Haz clic en **Labels**.
4. Al lado de la etiqueta que deseas eliminar, haz clic en **Delete**.

---

## 2. Creando un Pull Request

### Introducción a los Pull Requests

**Analogía:** Piensa en un pull request como una propuesta de matrimonio. Estás sugiriendo un cambio en el estado actual (tu relación) y necesitas la aprobación de tu pareja (el repositorio principal) para avanzar.

### Cambiando el Rango de Ramas y el Repositorio de Destino

Por defecto, los pull requests se basan en la rama principal del repositorio. Si necesitas cambiar el repositorio o la rama base, puedes hacerlo mediante listas desplegables al crear tu pull request.

### Creando el Pull Request

Para crear un pull request:

1. Navega a la página principal del repositorio en GitHub.
2. En el menú de "Branch", selecciona la rama que contiene tus cambios.
3. Haz clic en **Compare & pull request**.
4. Selecciona la rama base en la que deseas fusionar tus cambios y la rama de comparación.
5. Escribe un título y una descripción para tu pull request.
6. Haz clic en **Create Pull Request** para enviarlo para revisión.

### Consejos Útiles

- Después de crear un pull request, puedes solicitar la revisión de una persona específica.
- Un pull request se puede vincular a un problema para indicar que se está trabajando en una solución y cerrarlo automáticamente cuando se fusiona.

---

## Conclusión

Entender el manejo de etiquetas y la creación de pull requests en GitHub es fundamental en el camino para convertirte en un frontend developer. Usando analogías simples, hemos hecho más accesibles estos conceptos técnicos. ¡Ahora estás listo para aplicar estos conocimientos en tus proyectos!

---

# Roadmap to Becoming a Frontend Developer

## Managing Labels

### Introduction

Just like organizing your workspace helps you find your tools easily, managing labels on GitHub allows you to categorize issues, pull requests, and discussions effectively. This organization helps streamline collaboration and improves project management.

### About Labels

Labels are like tags that help you classify and organize your work in a GitHub repository. Once a label is created, you can use it on any issue, pull request, or discussion within that repository, just like putting a specific sticker on various boxes to identify their contents.

### About Default Labels

GitHub comes with default labels that can act as a foundation for your workflow. Think of these as the essential tools in a toolbox that you use regularly. Here are some default labels and their meanings:

| Label             | Description                                                      |
|-------------------|------------------------------------------------------------------|
| bug               | Indicates an unexpected problem or unintended behavior           |
| documentation     | Indicates a need for improvements or additions to documentation   |
| duplicate         | Indicates similar issues, pull requests, or discussions          |
| enhancement       | Indicates new feature requests                                    |
| good first issue  | Indicates a good issue for first-time contributors               |
| help wanted       | Indicates that a maintainer wants help on an issue or pull request|
| invalid           | Indicates that an issue, pull request, or discussion is no longer relevant |
| question          | Indicates that an issue, pull request, or discussion needs more information |
| wontfix           | Indicates that work won't continue on an issue, pull request, or discussion |

You can edit or delete these default labels later if they don’t fit your needs.

### Creating a Label

Creating a label is simple and can be done by anyone with write access to the repository. It’s similar to making a new tag for your project files. Here’s how:

1. Navigate to the main page of the repository.
2. Click on **Issues** or **Pull requests**.
3. Click on **Labels**.
4. Click **New label**.
5. Enter a name and description for your label.
6. Optionally, customize the color of your label.
7. Click **Create label**.

### Applying a Label

Applying labels is like putting a tag on your box after you’ve filled it. Anyone with triage access can do this:

1. Navigate to the issue, pull request, or discussion.
2. In the right sidebar, click **Labels**, then select a label.

### Editing a Label

If you need to change a label, it's as easy as updating the label on a box. Here’s how:

1. Navigate to the main page of the repository.
2. Click on **Issues** or **Pull requests**.
3. Click on **Labels**.
4. Click **Edit** next to the label you want to change.
5. Update the name or description, customize the color if needed, and click **Save changes**.

### Deleting a Label

If a label is no longer useful, you can remove it, similar to taking off an outdated sticker from your box. To delete a label:

1. Navigate to the main page of the repository.
2. Click on **Issues** or **Pull requests**.
3. Click on **Labels**.
4. Click **Delete** next to the label you want to remove.

---

## Creating a Pull Request

### Introduction

Creating a pull request is like submitting your homework for review. It allows others to collaborate on changes to a repository while keeping the main branch clean and stable.

### Who Can Use This Feature?

Anyone with read access to a repository can create a pull request, just as anyone in a study group can submit a draft for feedback.

### Changing the Branch Range and Destination Repository

Think of branches as different versions of your project. The main branch (often called `main` or `master`) is like the final version of a book, while feature branches are drafts. When creating a pull request, you can select which branches you want to merge, ensuring that only the right changes are applied.

### Creating the Pull Request

Here’s how to create a pull request:

1. Navigate to the main page of the repository.
2. Choose the branch that contains your commits from the "Branch" menu.
3. Click **Compare & pull request**.
4. Select the base branch (where you want the changes to go) and the compare branch (where your changes are).
5. Enter a title and description for your pull request.
6. Click **Create Pull Request**.

### Tips for Pull Requests

- After creating a pull request, you can ask someone specific to review your changes, just like asking a teacher to look over your work.
- If you need to, you can create a draft pull request first, allowing for preliminary discussions before it’s finalized.

### Conclusion

After the pull request is reviewed, it can be merged into the repository, much like receiving approval on your homework before it's added to the class record.

---

# Roadmap to Becoming a Frontend Developer

## Creating a Pull Request from a Fork

### Introduction

Creating a pull request from a fork is like submitting a proposal to make changes to a group project. Imagine you have a working document, and you want to suggest that certain modifications be incorporated into the main document.

### Who Can Use This Feature?

Anyone with write access to a repository can create a pull request from a fork. Think of it as having the permission from a teacher to make changes to their notebook.

If your pull request compares your working branch (also known as the "feature branch") with a branch in the original repository (the base branch), your working branch is called the "compare branch."

**Example:**
- Your working branch (or “feature branch”) is where you’re making changes in your forked repository (e.g., `my-topic-branch`).
- The base branch is the branch in the original repository where you want to merge your changes (e.g., `main`).
- The pull request compares the proposed changes from your working branch (`my-topic-branch`) with the base branch (`main`), so `my-topic-branch` is known as the "compare branch."

### How to Create a Pull Request

1. Navigate to the original repository where you created your fork.
2. Above the list of files, in the yellow banner, click **Compare & pull request** to create a pull request for the associated branch.
3. On the page to create a new pull request, click **compare across forks**.
4. In the "base branch" dropdown menu, select the branch of the original repository you'd like to merge changes into.
5. In the "head fork" dropdown menu, select your fork, then use the "compare branch" dropdown menu to select the branch you made your changes in.
6. Type a title and description for your pull request.

If you want to allow anyone with push access to the original repository to make changes to your pull request, select **Allow edits from maintainers**.

### Warning

If your fork contains GitHub Actions workflows, the option is **Allow edits and access to secrets by maintainers**. This also allows a maintainer to edit the workflows of the forked repository, which can potentially reveal secret values.

### Creating the Pull Request

To create a pull request that is ready for review, click **Create Pull Request**. To create a draft pull request, use the dropdown to select **Create Draft Pull Request**, then click **Draft Pull Request**.

**Tip:** After you create a pull request, you can ask a specific person to review your proposed changes.

---

## Inviting Collaborators to a Personal Repository

### Introduction

Inviting others to collaborate on your repository is like opening the door of your house to friends so they can help you organize a party. You can let them join in and contribute to the project.

### Who Can Use This Feature?

If you’re using GitHub Free, you can add unlimited collaborators to public and private repositories. Think of this as having a club where you can invite as many people as you want.

### About Collaboration in a Personal Repository

To collaborate with users in a repository that belongs to your personal account on GitHub, you can invite them as collaborators. It’s like allowing specific friends to access your toys to play together.

If you want to grant more granular access to the repository, you can create a repository within an organization.

### How to Invite a Collaborator

1. Ask for the username of the person you want to invite as a collaborator. If they don’t have a username yet, they can sign up for GitHub.
2. On GitHub, navigate to the main page of the repository.
3. Under your repository name, click **Settings**.
4. In the "Access" section of the sidebar, click **Collaborators**.
5. Click **Add people**.
6. In the search field, start typing the name of the person you want to invite, then click a name from the list of matches.
7. Click **Add NAME to REPOSITORY**.

The user will receive an email inviting them to the repository. Once they accept your invitation, they will have collaborator access to your repository.

### Important Note

GitHub limits the number of people who can be invited to a repository within a 24-hour period. If you exceed this limit, either wait 24 hours or create an organization to collaborate with more people.

---

# Roadmap to Becoming a Frontend Developer

## Adding Outside Collaborators to Repositories in Your Organization

Imagine you're the owner of a local bakery. You have a special recipe for your famous chocolate cake, but you want to let some friends help you bake it for a big event. In this scenario, your bakery represents your GitHub organization, the chocolate cake recipe is your repository, and your friends are the outside collaborators.

### Who Can Use This Feature?
Just like you, as the bakery owner, can choose who gets to help bake the cake, only people with admin access to a repository can add outside collaborators.

### About Outside Collaborators
An outside collaborator is someone who doesn't belong to your bakery (organization) but can help you bake (access) your special recipe (repository). You can choose how much access each friend gets—perhaps one can help with the mixing, while another is in charge of decorating.

When you invite an outside collaborator, remember that if your recipe is in a special vault (private repository), you might need to pay for extra storage (licenses). Also, if your bakery has a strict rule (two-factor authentication), your friends must follow it before they can join the baking team.

### Adding Outside Collaborators to a Repository
To allow your friends into the kitchen, you need to set it up in your bakery’s kitchen policy (repository settings). 

---

## About Issues

Now that you have your friends helping you, you need to keep track of what everyone is doing. This is where GitHub Issues comes in, like a whiteboard in your bakery where you write down tasks and ideas.

### Creating Issues
You can create issues in your repository to plan, discuss, and track work. It’s like jotting down ideas for new pastries, customer feedback, or any problems you might encounter while baking. You can also break your tasks into smaller pieces by adding sub-issues—like dividing the cake-making process into mixing, baking, and frosting.

### About Sub-Issues
Sub-issues are like creating a checklist for baking. For instance, if your main issue is "Bake Chocolate Cake," your sub-issues might include "Mix ingredients," "Bake for 30 minutes," and "Frost the cake." This helps everyone know exactly what needs to be done.

### Integration with GitHub
Just like mentioning a specific ingredient (issue) while discussing a recipe (pull request), GitHub allows you to create references between issues and pull requests. If you complete the task related to a specific issue, you can close it, just like crossing off an item from your checklist.

### Staying Up to Date
To keep everyone informed about the latest updates in your baking projects, you can subscribe to issues and get notifications when there are new comments or changes. This is similar to having a group chat where everyone shares progress.

### Community Management
To help your friends understand how to create useful tasks (issues), you can use templates. It’s like giving them a recipe card with specific instructions to ensure they provide all the information you need.

---

## Cloning and Forking Repositories on GitHub

When you want to try out a new cake recipe without risking your original recipe, you can make a copy. In GitHub, this is done through cloning and forking.

### What is Cloning?
Cloning is like making a photocopy of your special recipe so you can experiment at home. When you clone a repository, you create a local copy on your computer. This is useful when you want to work on a recipe with friends while still keeping the original safe.

To clone, head to the main page of the recipe (repository) and click the green "Code" button. You’ll have options for how to clone, like HTTPS, SSH, or GitHub CLI.

### What About Forking?
Forking is like taking your favorite recipe and making your own version of it. You can adjust the ingredients, add new flavors, or even create a whole new dessert without affecting the original recipe. A fork exists on GitHub, and while you can make changes, you can still send your improved recipe back to the original baker (repository) via Pull Requests.

Forking is easy! Just click the "Fork" button on the recipe page, and you'll have your own copy to work on, starting fresh while keeping the original intact.

### Final Note
Remember, when working with forks, if the original recipe (private repository) is deleted, your copy will also be removed. But for public recipes, your version remains yours, allowing you to innovate as you like!