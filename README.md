# STS195 Communal Space

> [!IMPORTANT]
> Please do not push to the `main` branch.
> If you find yourself with changes in main you want to move to another branch use:
>
> `git stash`
>
> `git checkout <branchname>`
>
> `git stash pop`

> [!CAUTION]
> Make sure to always use `git pull` before making changes to a git repo connected to GitHub!

## Goals

The goal of this All-class All-project repository is to encourage more collaboration between groups:

Suggestions:
1. Sharing documentation for projects (previous cohorts of students liked hearing about what others were doing during standups - otherwise, they were isolated to their different groups)
2. Sharing resources/collaborating
3. Sharing student-made functions
4. Sharing code for visualizations they are excited about
5. Asking questions and troubleshooting with reproducible data

## Practice Pull Requests via Project README Set up

- Make an issue (Remote/GitHub)
  - Title the issue "<YourName>'s README issue"
  - In the description, add some details on what you are doing and why
- Clone this repo (Local/Git)
  - `git clone <gitrepo>`
  - `cd 2025-STS-195`
- Create a branch using your name (Local/Git)
  - `git branch`
  - `git checkout -b <yourname>`
  - `git branch`
- Create a draft README file (Local/Git)
  - basic overview of your project
  - what you would want other students to know about it
  - short, simple pitch for the project
  - `vi README-<yourname>.md`
    >```
    ># A Title Header has one #
    >
    >## A section header has ##
    >A short and simple pitch of what I understand about my project is ...
    >
    >```
    [Please review markdown formatting for more tricks](https://github.com/im-luka/markdown-cheatsheet)
  - `git status`
  - `git add <readme-file>`
  - `git commit -m "adding my readme file"`
  - `git log`
  - `git push` or `git push -u origin <yourname>`
- Create a pull request (Remote/GitHub)
  - Find your branch (Green dropdown on the upper left)
  - Click `Contribute` > `Open pull request`
  - Title "Adding <yourname>'s readme markdown file for posterity"
    - Optionally include [WIP] or [MRG] to preface your title (Explain the current intention of the pull request)
  - Add a description and [make sure to include](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue):
    - `closes, closed, fix, fixes, fixed, resolve, resolves, or resolved`
    - followed by your issue number
      - `fixes #1`
    - This may only work if in the first discussion section of a pull request(?). Not the replies?
- Merge the pull request into the main branch

## Using Issues

Issues may be more than their name. They can become a repository of code snippets and discussions. This information becomes easily searchable and allows you to jump quickly to the information you need. 
This can be enhanced by linking similar issues with the `#` and the issue number.  

Try adding interesting material and links to an issue.

## Best practices

IDK, let me think on it for a while

1. protecting main branch
2. after pull request delete head branches
3. watching for updates
