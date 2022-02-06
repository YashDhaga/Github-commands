# __Github commands__

### To upload projects to github:-

> git config --global user.name [userName]

> git config --global user.name [emailId]

> git init

> git add .

> git commit -m "Initial commit"

> git status

> ssh-keygen -t rsa -b 4096 -C "emailId"

> tail [path to id_rsa.pub]

    Add this key to your github account.

> git remote add origin [ssh url.git]

> git push origin master

---

## ___Commands explained:-___


### SETUP

Configuring user information used across all local repositories

> git config --global user.name “[firstname lastname]”

    Set a name that is identifiable for credit when reviewing version history.

> git config --global user.email “[valid-email]”

    Set an email address that will be associated with each history marker.

> git config -l

    The command returns a list of information about your git configuration including user name and email.

> git config --global color.ui auto

    set automatic command line coloring for Git for easy reviewing.

---

### SETUP & INIT

Configuring user information, initializing and cloning repositories

> git init

    Initialize an existing directory as a Git repository

> git clone [url]

    Retrieve an entire repository from a hosted location via URL. (Creates a new folder by default)

OR

> git clone [url] [folderName]

    [folderName] - To clone a repo in a specific folder.

### STAGE & SNAPSHOT

Working with snapshots and the Git staging area

> git status

    Show modified files in working directory, staged for your next commit

> git status -s

    A shorthand representation of git status.

> git add [file]

    Add a file to the staging area.

> git add .

    To add all files in your project to the staging area.

> git reset [file]

    Unstage a file while retaining the changes in working directory

> git diff

    diff of what is changed but not staged

> git diff --staged

    diff of what is staged but not yet commited

> git commit

    Opens a text editor in the terminal where you can write a full commit message.

> git commit -m "[descriptive message]"

    To add a commit message without opening the editor.
    This command lets you only specify a short summary for your commit message.

> git commit -a -m "commit directly without staging area"

---

### BRANCH & MERGE

Isolating work in branches, changing context, and integrating changes

> git branch

    list your branches. a * will appear next to the currently active branch

> git branch [branch-name]

    create a new branch at the current commit

> git branch -d branch_name

    When you are done working with a branch and have merged it, you can delete it using the command below:

> git checkout

    switch to another branch and check it out into your working directory

> git checkout -b [branchName]

    Create a new branch and switch to it simultaneously.

> git merge [branch]

    merge the specified branch’s history into the current one

> git log

    show all commits in the current branch’s history

---

### INSPECT & COMPARE

Examining logs, diffs and object information

> git log

    show the commit history for the currently active branch

> git log branchB..branchA

    show the commits on branchA that are not on branchB

> git log --follow [file]

    show the commits that changed file, even across renames

> git diff branchB...branchA

    show the diff of what is in branchA that is not in branchB

> git show [SHA]

    show any object in Git in human-readable format

---

### TRACKING PATH CHANGES

Versioning file removes and path changes

> git rm [file]

    delete the file from project and stage the removal for commit.
    This command expects a commit message to explain why the file was deleted.

> git rm --cached [file name]

    The --cached flag lets you delete a file from a Git repository without deleting it on your file system.

> git mv [existing-path] [new-path]

    Change an existing file path.
    This command stages the changes, then it expects a commit message.

> touch .gitignore

    To ignore files in Git.
    Put files/folders in .gitignore which you dont want to push.

> git log --stat -M

    show all commit logs with indication of any paths that moved

---

### SHARE & UPDATE

Retrieving updates from another repository and updating local repos

> git remote add [alias] [url]

Eg:-

> git remote add origin [url]

    add a git URL as an alias.
    Here, origin is the alias.

> git remote -v

    gives the url of the remote repository.

> git fetch [alias]

    fetch down all the branches from that Git remote

> git merge [alias]/[branch]

    merge a remote branch into your current branch to bring it up to date

> git push -u origin [branchName]

    Transmit local branch commits to the remote repository branch.
    (Benefit of -u tag)
    Next time, we can simply write
    git push, and it will push [branchName] to origin automatically.
    Thus, we wont have to specify origin [branchName] everytime.

> git pull

    If other team members are working on your repository, you can retrieve the latest changes made to the remote repository with this command.

---

### REWRITE HISTORY

Rewriting branches, updating commits and clearing history

> git reset --hard [commit]

    clear staging area, rewrite working tree from
    specified commit

---

### TEMPORARY COMMITS

Temporarily store modified, tracked files in order to change branches

> git stash

    Save modified and staged changes

> git stash list

    list stack-order of stashed file changes

> git stash pop

    write working from top of stash stack

> git stash drop

    discard the changes from top of stash stack
