# GIT DOCUMENTATION AND BASIC CHEAT SHEET
[GIT](git-scm.com) is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.



## 01 QUICK START
In GIT, a remote repository is a version of your project hosted on a server (such as GitHub or Azure DevOps). It allows collaboration, sharing and synchronization with other developers.


### SETTING UP A NEW REPOSITORY
```BASH
touch README.md
git init
git add README.md
git commit -m "Initial Commit"
git branch -M main
git remote add origin <project url>
git push -u origin main
```
`git remote add` is used when you want to **connect your local repo to a remote repo**. It **adds a reference** to the remote repository in your local configuration. This method for connecting repos is most commonly used when you've already created a local repo and want to link it to an existing remote repo or when you want to push your changes to a specific remote (e.g. your own fork of a project).


### SETTING UP AN EXISTING REPOSITORY
```BASH
git clone <project url>
```
`git clone` is used when you want to **create a new local copy of an entire remote repo**. It **downloads the entire repo**, including all branches, commits, and files. This method for connecting repos is most commonly used when you're starting a new project and want to work with an existing codebase or when you want to contribute to an open-source project through the cloning of its repository.


## 02 GIT CONFIGURATION
```BASH
git config --global user.name "Your Name"
```
Set the name that will be attached to your commits and tags.

```BASH
git config --global user.email "you@example.com"
```
Set the e-mail address that will be attached to your commits and tags.



## 03 STARTING A PROJECT
```BASH
git init [project name]
```
Create a new local repository in the current directory. If **[project name]** is provided, Git will create a new directory named **[project name]** and will initialize a repository inside it.

```BASH
git clone <project url>
```
Downloads a project with the entire history from the remote repository.

### REMOTE ADD vs CLONE
`git clone <project url>` will physically download the files from the attached URL, along with any branches in the repo, to the computer's drive.

`git remote add <project url>` acts more like a pointer to the remote repo. It isn't until a `git fetch` or `git pull` that files are downloaded from the remote repo.



## 04 DAY-TO-DAY WORK
| COMMAND | DESCRIPTION |
| --- | --- |
| `git status` | Displays the status of your working directory. Options include new, staged, and modified files. It will retrieve branch name, current commit identifier, and changes pending commit. |
| `git add [file]` | Add a file to the **staging** area. Use `.` in place of the full file path to add all changed files from the **current directory** down into the **directory tree**. |
| `git commit -m "commit message"` | Create a new commit from changes added to the **staging area**. The **commit** must have a message! |
| `git rm [file]` | Remove file from **working directory** and **staging area**.|
| `git diff [file]` | Show changes between **working directory** and **staging area**. |
| `git diff --staged [file]` | Shows any changes between the **staging area** and the **repository**. |
| `git checkout -- [file]` | Discard changes in **working directory**. This operation is **unrecoverable**. |
| `git reset [<path>...]` | Revert some paths in the index (or whole index to their state in **HEAD**. |



## 05 SYNCING REPOS
| COMMAND | DESCRIPTION |
| --- | --- |
| `git fetch [remote]` | Fetch changes from the **remote**, but not update tracking branches. |
| `git pull [remote]` | Fetch changes from the **remote** and merge current branch with its upstream. |
| `git push [remote]` | Push local changes to the **remote**. Use **--tags** (before remote) to push tags. |
| `git push -u [remote] [branch]` | Push local branch to **remote** repository. Set its copy as an upstream. |


### PULL vs FETCH
`git pull` tries to merge after fetching commits. It is *context sensitive*, so all pulled commits will be merged into the active branch. `git pull` automatically merges the commits **without reviewing first**. Conflicts are frequent when branches aren't carefully managed. In the most simple terms, `git pull` does a `git fetch` followed by a `git merge` all in one.

`git fetch` gathers any commits from the target branch that do not exist in the current branch and **stores them in the local repository**. However, **it does note merge them with the current branch**. Used to keep local repo up to date with the remote repo, without writing over local changes. To integrate the commits from the remote repo into the current branch, `git merge` must be used.


### WORKFLOW
![alt text][general workflow image]



## 06 GIT BRANCHING
This is one of those things where I'm going to write a whole bunch of command's and their various descriptions, heck I might even include an image...

Just look up a video, it'll save you so much more time and maybe reduce suffering who knows.



## 07 INSPECT HISTORY AND REVERTING CHANGES
| COMMAND | DESCRIPTION |
| --- | --- |
| `git log [-n count]` | List commit history of current branch. **-n count** limits list to last **n** commits. |
| `git log --one line --graph --decorate` | An overview with reference labels and history graph. One commit per line. |
| `git log ref ..` | List commits that are present on the current branch and not merged into **ref**. A **ref** can be a branch name or a tag name. |
| `git log .. ref` | List commit that are present on **ref** and not merged into current branch. |
| `git reflog` | List operation (e.g. checkouts or commits) made on local repository. |
| `git reset [--hard] [target reference]` | Switches the current branch to the **target reference**, leaving a difference as an uncommitted change. When **--hard** is used, all changes are discarded. It's easy to lose uncommitted changes with **--hard**. |
| `git revert [commit sha]` | Create a new commit, reverting changes from the specified commit. It generates an **inversion** of changes. |



## 08 TAGGING COMMITS
| COMMAND | DESCRIPTION |
| --- | --- |
| `git tag` | List all tags. |
| `git tag [name] [commit sha]` | Create a tag reference named **name** for current commit. Add **commit sha** to tag a specific commit instead of a current one. |
| `git tag -a [name] [commit sha]` | Create a tag object named **name** for current commit. |
| `git tag -d [name]` | Remove a tag from local repository |


### LIGHTWEIGHT vs ANNOTATED
A lightweight tag is very much like a branch that doesn’t change — it’s just a pointer to a specific commit.

Annotated tags, however, are stored as full objects in the Git database. They’re checksummed; contain the tagger name, email, and date; have a tagging message; and can be signed and verified with GNU Privacy Guard (GPG). It’s generally recommended that you create annotated tags so you can have all this information; but if you want a temporary tag or for some reason don’t want to keep the other information, lightweight tags are available too.



[GitLab Cheat Sheet](https://about.gitlab.com/images/press/git-cheat-sheet.pdf)

[general workflow image]: https://i.sstatic.net/qPcFI.png
