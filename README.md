# R in Jupyter

This repository provides a template for any teaching requiring R in a Jupyter Notebook.
It is designed to be run through a GitHub Codespace (the config sits in `devcontainer`),
but you can prepare a local setup using the instructions at the bottom of this page.

> [!IMPORTANT]  
> Consider editing or removing `README` and `sample-notebook`s before sharing with students.

## RMarkdown to Jupyter

In Jupyter (`ipynb`), you can create two broad types of *cells* - **Markdown** and **Code** -
by hovering above or below a current cell, or by using the menu at the top of the window.

To change from RMarkdown to Jupyter, copy code from between the Rmd code fences ```{r} and ```
(but not the fences themselves) and paste it into ipynb **Code cells**. Everything else is Markdown
so can be copied across into **Markdown cells**.

Chunk options (for example to silence warnings or add captions) are different in Jupyter. You
can read up on them [here](https://quarto.org/docs/reference/cells/cells-jupyter.html).

See the `sample-notebook` files in this repository for an example of converting between the
formats.

## GitHub

You can fork or create a repository from this template and add your own materials. To save,
use the **Source Control** button in the left sidebar, **write a message in the text box**,
and click **Commit & Sync**. 

When you have populated the repository with content, from the main page of your repository,
go to **Settings** and tick **Template repository**. This will allow you to share with students
via Classroom.

Students can engage with their version of the repository in the same way (creating a template),
but it is generally recommended to share a repository with students using GitHub Classroom Assignments.

If you are looking for a very basic introduction to Codespaces, consider sharing the repository
at [this link](https://github.com/Imperial-Business-School/codespace-getting-started), which
can be opened in a Codespace or used as a Classroom Assignment. 

## Classroom

[GitHub Classroom](https://classroom.github.com/classrooms) uses *Assignments* to
distribute *starter code* to students with a simple link. You will need to be added to the
Imperial-Business-School organisation, which supports creating new Classrooms.

Create a new Classroom for your module and then create an Assignment. Give it a name and
if it will be an assessed piece of work, you can optionally add a deadline. On the next page,
under **Starter Code** choose the repository that you created in the previous step.

Students first have to connect their GitHub account to their Imperial account. Share the
following instructions with them before sharing any Classroom links.

1. Go to [this GitHub link](https://github.com/orgs/ImperialCollegeLondon/sso).
2. Click Continue.
3. Sign in with your Imperial credentials.
4. When prompted to create a GitHub account, you can either create a new GitHub account or use an existing one. We recommend using a personal email address for your GitHub account so you can continue to use the account after leaving Imperial.

Troubleshooting:
- Creating a new GitHub account using an Imperial email address does not link the accounts
- A maximum of one GitHub account can be linked to an Imperial account
- A common problem is a student with multiple accounts trying to accept an Assignment with a non-linked account


## R, VS Code, Jupyter - Locally

For anyone wishing to replicate this setup locally, these are the instructions:

1. [Install R](https://cloud.r-project.org) (>= 3.4.0)

2. [Install VS Code](https://code.visualstudio.com/download)

3. In R, install the `languageserver` and `IRkernel` packages. 
    <br>Then run `IRkernel::installspec()`

    ```R
    install.packages('languageserver')
    install.packages('IRkernel')
    IRkernel::installspec()
    ```

4. In VS Code, search for and install the following extensions:
    - R (REditorSupport)
    - Jupyter (Microsoft)
    - R Arrow Operator (Jay)
    - PDF Viewer (Mathematic Inc)

### To render PDF from Jupyter

1. [Install Quarto](https://quarto.org/docs/get-started/)

2. Install TinyTex with Quarto

    ```bash
    quarto install tinytex
    ```

3. Use the `Render to PDF` button at the top of the Notebook, or run

    ```bash
    quarto render path_to_notebook.ipynb --to pdf
    ```
