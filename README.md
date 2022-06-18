# git and github

## What is git?

<em><span style="color: #FF7F50; font-size: 26px">"GIt</span> is software for **tracking changes** in any set of files,</br> usually used for **coordinating work** among programmers collaboratively developing source code during software development<em><span style="color: #FF7F50; font-size: 26px">"</span></em></em>

**∴** **<span style="color: #FF7F50;">Git is a version control system</span>**

## so how does git works?

-   **Repository** is a container for a project which can be stored locally or on a website such as github (remote repository)
-   **Working directory** is where you are working on a project in the local computer. You can save changes while modifying your project but they are **not yet tracked**, thus not ready for commit
-   **Git add** command adds change in the working directory to the **staging area** ready for commit
-   **Commits** are **save points** for the project. commit **hashes** are unique key generated by git. **commit history** saves all the commits (ex. **tracked changes** implemented in the project)
-   **Git push** **uploads** commits to the remote repository at Github
-   **Git pull** **fetch and download** changes from the remote repository to local repo

<span style="display: block; text-align: center;">![Git Push](https://user-images.githubusercontent.com/102004753/174426626-ccc09536-dee8-4810-b1c4-4051ab545fde.png)
</span>

## git workflows

git workflow is **best-practice** for how to use Git in a **consistent** and **effective** manner. </br> There are many ways.

One typical way is the following:

-   clone or pull latest change from the main
-   create a new branch for fixing bug
-   modify the files in your local computer
-   commit changes to your branch
-   squash all commits into one single commit and get reviewed (once PR)
-   merge to main branch (from this point you can delete the branch)

<span style="display: block; text-align: center;">![Git branch](https://user-images.githubusercontent.com/102004753/174427046-6c9bb3bd-2db4-4f33-acb3-ebf737f51544.png)
</span>

**Merge Conflict**
because main branch will move on as you are working on your branch, there are times where your PR will face "merge conflict issue"
(especially when the changes are made in same lines)

## git commands

-   checks git version

```bash
git --version
```

-   see all common git commands

```bash
git --help
```

-   clear git bash terminal

```bash
Ctrl + l
```

-   break from git bash

```bash
q
```

-   goes into Desktop

```bash
cd Desktop
```

-   list all folders/ files in the current directory

```bash
ls
```

-   create folder

```bash
mkdir <folder name>
```

-   go out of current directory

```bash
cd ..
```

-   create empty git repo (for brand new project only)

```bash
git init .
```

-   lists all the files in the directory

```bash
la -a
```

-   delete git file

```bash
rm -rf .git
```

-   create file

```bash
touch index.html
```

-   add files individually

```bash
git add <filename>
```

-   add all files from this directory (downwards)

```bash
git add .
```

-   shows the status of the changes we made (all untracked files)

```bash
git status
```

-   to unstage files that we added

```bash
git rm --cached <filename>
```

-   to unstage all files from staging area

```bash
git rm -r --cached
```

-   create save points

```bash
git commit -m "messages"
```

-   see commit history

```bash
git log
```

-   see commit history in oneline

```bash
git log --oneline
```

-   see individual commit

```bash
git show <commit hash>
```

-   go into file and change from bash

```bash
vi index.html
```

-   to insert after vi

```bash
i
```

-   to exit after vi

```bash
ESC + :wq
```

-   view file content

```bash
cat <filename>
```

-   to compare diff

```bash
git diff
```

-   to push directly to main (not advisable, use PR)

```bash
git push -u origin main
```

-   to upload

```bash
git push
```

-   to fetch and download

```bash
git pull
```

-   see branches

```bash
git branch
```

-   see branches in remote

```bash
git branch -r
```

-   see all branches (local + remote)

```bash
git branch -a
```

-   create a new branch

```bash
git branch <branch-name>
```

-   switch to branch

```bash
git checkout <branch-name>
```

-   switch back to previous branch

```bash
git checkout -
```

-   switch to branch

```bash
git checkout <branch-name>
```

-   create branch and switch at the same time

```bash
git checkout -b <branch-name>
```

-   squash last three commits (example)

```bash
git reset --soft HEAD~3
```

-   rebase from main

```bash
git pull -r origin main
(and then, solve merge conflict)
git add .
git rebase --continue
git push -f
(even if it warns that the current branch is behind its remote counterpart,
it is not hence,)
git push -f
```

## why rebase?

For one overriding reason: maintaining a linear project history. Let's say for instance that you've been working on a feature branch off the main branch, but the latter has progressed. But you want to get the main branch's latest updates into your feature branch while keeping your branch's history clean, so it looks like you've been working off the updated, latest main branch.

## what is SSH-key?

When working with a GitHub repository, you'll often need to identify yourself to GitHub using your username and password. An SSH key is an alternate way to identify yourself that doesn't require you to enter you username and password every time.

-   [Github guide to ssh-key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## Sources:

-   [Amigoscode](https://www.youtube.com/watch?v=3fUbBnN_H2c)
-   [SSH-key](https://www.youtube.com/watch?v=3aKda-oXWc8&t=261s)
