# Cookiecutter DCB0129 Clinical Safety Management File

Powered by [Cookiecutter](https://github.com/cookiecutter), the Cookiecutter DCB0129 Clinical Safety Management File automates the generation of a skeleton outline DCB0129-compatible Clinical Safety Management File, pre-populated with project-, team-, and organisation-specific details.

## Features

- **DCB0129 Documents** - Automatic generation of a skeletal set of clinical safety documents to be reviewed fully, and customised for the use-case.
- **Documentation Website** - Repo is with a ready-configured Material for MkDocs website to show your clinical safety documents openly.
- **GitHub Pages** - Automatic build and deploy of the MkDocs site as a GitHub Pages site (via GitHub Actions)
- **PDF Export** - Automatic generation of a PDF version of the complete site, for organisations who would prefer to have an 'offline' document.
- **Hazard Log** - GitHub Action to generate standard DCB1029-compatible Labels for Hazard Severity and Likelihood, as well as overall Risk level.

## Why?

We believe that creation of the DCB0129 Clinical Safety Management File using traditional methods (for example customising the NHS Digital template Word documents) is unnecessarily time-consuming and distracts Clinical Safety Officers from the **actual** task of building clinical safety into the development toolchain and working with their teams on improving the safety of their products.

Having used GitHub for managing clinical safety documentation in other projects, we have developed this Cookiecutter to speed up the initial process of creating a new GitHub repository and some clinical safety documentation to start from.

---

> ## **DISCLAIMER**

> **This documentation is offered as a free public service to other Clinical Safety Officers as-is, without warranty of any kind. It in no way replaces the need for a comprehensive and legal clinical safety team approach. All responsibility for all aspects of clinical safety compliance and legal compliance remains with the owners of the Healthcare IT project.**

---

## Usage

### Setup

Install [Cookiecutter](https://github.com/cookiecutter/cookiecutter) and any prerequisites such as Python.

### Initial generation of clinical safety management file

Run the Cookiecutter

```shell
cookiecutter gh:bawmedical/cookiecutter-dcb0129
```

Enter your project-, team- and organisation-specific information in response to the command line prompts.

The data you enter will be used to populate values within the template documents, and the output will be in a subfolder named according to your _slugified_ project name plus `-clinical-safety-management-file`. So a project called 'Project Mayhem' will have a slug of `project-mayhem-clinical-safety-management-file`.

### Commit to version control

Enter the directory generated by Cookiecutter
`cd project-mayhem-clinical-safety-management-file`

Initialise a Git repository in the folder which Cookiecutter has generated.
`git init`

Create a repository on GitHub to house your new repository and follow the instructions for connecting to the GitHub remote from your local machine, which will be something like `git remote add origin <MYREPONAME>`

Push local changes to the remote
`git push -u origin main`

### Creating the standard palette of Hazard Log labels

Once the repo is pushed to GitHub, a GitHub Action will have been created which automates the process of removing unwanted Issue labels and replaces them all with the labels for Likelihood, Severity, and Risk Level

To make this happen is a one-time task in GitHub. Navigate to your GitHub repository, go to the Actions tab, and select 'create-hazard-log-labels' from the right sidebar. Over on the right of the page is a button labelled 'Run workflow', click this and the labels will be created. All other labels will be removed, but you can easily add any other custom labels you need later in the Labels UI.

### Enabling the built-in Material for MkDocs website

Go into GitHub's repository settings and enable GitHub Pages for your repository (This only works with public repos unless you have a paid plan). Enable GitHub Pages to build from the `gh-pages` branch of your repository.

You may notice (if you look at graphical representations of the Git branches in something like Git Graph on VS Code) that the `gh-pages` branch is completely unrelated to the other branches you may have - this is because the ['build-and-deploy' GitHub Action workflow](https://github.com/bawmedical/cookiecutter-dcb0129/blob/main/%7B%7Bcookiecutter.__project_slug%7D%7D-clinical-safety-management-file/.github/workflows/build-and-deploy-to-gh-pages.yml) force-pushes the built HTML site to that branch.

### Making Changes

You can edit any part of the generated documentation in a text editor. We recommend [Visual Studio Code](https://code.visualstudio.com/), which is a free, extensible, open source editor. Global 'find and replace' is the easiest way to make global changes if you need to amend any of the global variables you set during the initial Cookiecutter run.

### Online Markdown editing

If you are new to Markdown editing, you can use GitHub's interface itself to edit online, by clicking the 'pencil' edit icon in the top right corner of any source code page. There are also external tools like [Prose.io](http://prose.io/) and [StackEdit](https://stackedit.io/) which give you a nice interface for editing MarkDown online, and will sync the changes with GitHub for you. If you need help getting set up, [contact us in the Signal chat](../contact/contact.md).

### Reviewing and amending

You **MUST** review and amend **IN ENTIRETY** the generated clinical safety documentation according to the needs of your project, team, and organisation. The auto-generated documentation is only a starting point for you clinical safety documentation, it is designed to speed up, simplify, and improve your clinical safety work, but **it is not a replacement for a Clinical Safety Officer and an appropriate clinical safety process.**

- Remove any documents that you don't need.
- Review all the documents to ensure they read correctly and make sense.
- Add any documents

### Output into other formats

Some organisations or collaborators will be uncomfortable with the Markdown format used here, and may prefer to consume this documentation as a PDF or Word document.

When the website is pushed to GitHub, a PDF rendering of the entire site is created and saved to the `pdf/` folder in the `gh-pages` branch. This branch is the one which is deployed to GitHub Pages, so the button on the Download page in the documentation site will work.

Somehow (don't ask me how) this button also works when using `mkdocs serve` on your local machine. :-)

## Contributing

If you have suggestions, amendments, or improvements to contribute, these are most welcome. Probably the best way to start a conversation is to [open an Issue](https://github.com/bawmedical/cookiecutter-dcb0129/issues) on this repository. [Pull requests](https://github.com/bawmedical/cookiecutter-dcb0129/pulls) will be considered as well, if they enhance the overall project.

## Roadmap for future development

- Support for Medical Device Registration Documentation in EU, UK, and NI.
- Support for Digital Technologies Assessment Criteria (DTAC).

## Acknowledgements

- This Cookiecutter is derived from the Clinical Safety work from the RCPCH Digital Growth Charts project, the RCPCH Epilepsy12 Audit Platform project, and other RCPCH Incubator and Baw Medical Ltd projects, for which due acknowledgement is afforded.

## Authors

- **Dr Marcus Baw** [@pacharanero](https://github.com/pacharanero)
