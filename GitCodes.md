# The initial configuration
| Command                                   | Description                                                  |
| ----------------------------------------- | ------------------------------------------------------------ |
| git config --list                         | Show a list of the configurations                            |
| git config --global user.name “user name” | set up a name or username for credit when reviewing version history |
| git config --global user.email “email”    | set up an email address that will be associated with each bookmark |
```
$ git config --global user.name “My Username”
$ git config --global user.email “MyEmail@MyEmail.com”

$ git config --list
user.name="My Username"
user.email="MyEmail@MyEmail.com”
```
When you enter git for the first time you need to configure your username and email so that the projects and commits you make are credited to you
# Start a new project
## Starting a project from zero 
To create a project from scratch you use a simple command
| Command  | Description                                        |
| -------- | -------------------------------------------------- |
| git init | Used to initialize a directory as a git repository |
```
C:\User\Example
$ mkdir NewProject

C:\User\Example\NewProject
$ git init
```
In this example we create a new directory to create the new project
## Cloning an existing repository
On the other hand, if what you want is to clone a project, it is done as follows
| Command         | Description                                                  |
| --------------- | ------------------------------------------------------------ |
| git clone [url] | used to retrieve a repository from a hosted location via URL |

```
C:\User\Example
$ git clone https://github.com/hd-garcia-manzo/Git-github

C:\User\Example\NewProject
$ cd Git-github

C:\User\Example\NewProject\Git-github
```
After cloning the repository we must enter the created folder

# Basic workflow commands
## The status
| Command    | Description                                                  |
| ---------- | ------------------------------------------------------------ |
| git status | shows modified files, added files, and missing files to be added to the working directory, ready for their next commit |
```
C:\User\Example\NewProject
$ ls 
file1.txt file2.txt file3.txt

C:\User\Example\NewProject
$ git status

On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   file1.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file2.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file3.txt
```
In the example we can see a file that has already been added to the staging area and is ready for the commit, another file that was modified but not yet added to the staging area so if a commit is made this file would not appear, and finally an untracked file that is also not ready for a commit

## Adding files
| Command        | Description                   |
| -------------- | ----------------------------- |
| git add [file] | add a file to the next commit |

To add the missing files we will do the following
```
C:\User\Example\NewProject
$ git add file2.txt
$ git add file3.txt
```
Or we can also do it in the following way
```
C:\User\Example\NewProject
$ git add *.txt
```
In this last example all files with extension .txt are added
```
C:\User\Example\NewProject
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   file1.txt
        modified:   file2.txt
        new file:   file3.txt
```
We can see that now all files are ready for commit

## Unstage a file
| Command          | Description                                                  |
| ---------------- | ------------------------------------------------------------ |
| git reset [file] | Unstage a file while retaining the changes in working directory |
```
C:\User\Example\NewProject
$ git reset file2.txt

C:\User\Example\NewProject
$ git status

On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   file1.txt
        new file:   file3.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file2.txt
```
As we can see, file 2 is no longer ready for the commit but retains its modifications

## Diff command
| Command           | Description                                |
| ----------------- | ------------------------------------------ |
| git diff          | To see what is changed but not staged      |
| git diff --staged | To see what is staged but not yet commited |

```
C:\User\Example\NewProject
$ git diff

The file will have its original line endings in your working directory
diff --git a/file2.txt b/file2.txt
index 1f0b5e9..8bfd952 100644
--- a/file2.txt
+++ b/file2.txt
@@ -1,2 +1 @@
-This is old text
+This is the modified text

C:\User\Example\NewProject
$ git diff --staged

diff --git a/file1.txt b/file1.txt
index 72dd871..fa53936 100644
--- a/file1.txt
+++ b/file1.txt
@@ -1,2 +1,4 @@
This is old text
+This is the modified text

diff --git a/file3.txt b/file3.txt
new file mode 100644
index 0000000..8bfd952
--- /dev/null
+++ b/file3.txt
@@ -0,0 +1 @@
+This is the modified text
```
## Commit command
| Command                               | Description                                                  |
| ------------------------------------- | ------------------------------------------------------------ |
| git commit -m “[descriptive message]” | used to confirm your content as a new confirmation snapshot  |
| git commit --amend                    | used to modify a previous commit when small changes were made |

```
C:\User\Example\NewProject
$ git commit -m "First commit"

[master ca7685d] First commit
 2 files changed, 3 insertions(+)
 create mode 100644 file3.txt
```
As you can see, it tells us that only 2 files were changed, this is because as you remember in the previous examples, we removed file2 and did not add it again, to modify a previous commit we will do the following.
```
C:\User\Example\NewProject
$ git add file2.txt

C:\User\Example\NewProject
$ git commit --amend

[master 6f081f8] First commit
 Date: Wed Apr 21 12:57:48 2021 -0500
 3 files changed, 4 insertions(+), 2 deletions(-)
 create mode 100644 file3.txt
```
An editor is displayed, press ESC and then enter: q! to go out

## Log command
| Command | Description                                      |
| ------- | ------------------------------------------------ |
| git log | show all commits in the current branch’s history |

```
C:\User\Example\NewProject
$ git log
commit XXXXXXXXXX
Author: “Username” <“Usermail@usermail.com”>
Date:   Wed Apr 21 12:57:48 2021 -0500

    First commit
```

# Push to a remote repository
To do this we must have an active account on github, then we are going to create a new repository.

Once that is done we will return to our command line and do the following

| Command                     | Description                                                  |
| --------------------------- | ------------------------------------------------------------ |
| git branch -M main          | Make sure we are in the main branch                          |
| git remote add origin [URL] | Add a git URL as an alias                                    |
| git push -u origin main     | Transmit local branch commits to the remote repository branch |

```
C:\User\Example\NewProject
$ git branch -M main

C:\User\Example\NewProject
$ git remote add origin https://github.com/hd-garcia-manzo/RepoExample.git

C:\User\Example\NewProject
$ git push -u origin main

```
And you can check it by entering the URL you added, there you will find the files that we added in the commit

| Command                                                      | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| git remote -v                                                | shows you where you are getting the repositories from        |
| git fetch [Nickname from where you are getting the repositories] | get the data of latest version that is uploaded to a remote repository |
```
C:\User\Example\NewProject
$ git remote -v
origin  https://github.com/hd-garcia-manzo/Git-github.git (fetch)
origin  https://github.com/hd-garcia-manzo/Git-github.git (push)
```

# Branches: create, delete, save/commit & merge
| Command                 | Description         |
| ----------------------- | ------------------- |
| git branch --list       | list your branches  |
| git branch [BranchName] | Create a new branch |


```
C:\User\Example\NewProject (master)
$ git branch --list 
*master

C:\User\Example\NewProject (master)
$ git branch test

C:\User\Example\NewProject (master)
$ git branch --list 
* master
 test
```
| Command                   | Description                                                  |
| ------------------------- | ------------------------------------------------------------ |
| git checkout [BranchName] | switch to another branch and check it out into your working directory |

```
C:\User\Example\NewProject (master)
$ git checkout test
Switched to branch 'test'

C:\User\Example\NewProject (test)
$ git checkout -b test2
Switched to a new branch 'test2'

C:\User\Example\NewProject (test2)
$ git branch --list 
 master
 test
 * test2
```

As you can see, we can also use this command to create a new branch
| Command                    | Description     |
| -------------------------- | --------------- |
| git branch -d [BranchName] | remove a branch |
```
C:\User\Example\NewProject (master)
$ git branch -d test2
Deleted branch test2

C:\User\Example\NewProject (master)
$ git branch --list 
* master
  test
```
Now suppose the following scenario, in the master branch we have file1, file2 and file3 and in the test branch we have the same file3 but with a modification (In the example I will put it as "file3modified" to differentiate it but in reality it is called file3)

To make a commit in a different branch, it is done in the same way, which is the following
```
C:\User\Example\NewProject (test)
$ ls
file1.txt file2.txt file3modified.txt

C:\User\Example\NewProject (test)
$ git add file3modified.txt

C:\User\Example\NewProject (test)
$ git commit -m "Test branch first commit"

$ git log
commit XXXXXXXXX (HEAD -> test)
Author: “Username” <“Usermail@usermail.com”>
Date:   Wed Apr 21 14:05:10 2021 -0500

    test branch first commit

commit XXXXXXXXX (master)
Author: “Username” <“Usermail@usermail.com”>
Date:   Wed Apr 21 12:57:48 2021 -0500

    First commit

```

As you can see, our previous commit appears and our new commit also appears in the test branch

Now we are going to combine both commits

| Command                | Description                                               |
| ---------------------- | --------------------------------------------------------- |
| git merge [BranchName] | merge the specified branch’s history into the current one |

```
C:\User\Example\NewProject (master)
$ git merge test
Updating XXX..XXX
Fast-forward
 file3.txt | 2 ++
 1 file changed, 2 insertions(+)

```

# Gitflow

The Gitflow workflow defines a strict branching model designed around project publishing. Provides a solid framework for managing larger projects.

This workflow does not add any new concepts or commands beyond what is needed for the function branch workflow.

The git-flow installation process is straightforward. The git-flow packages are available on various operating systems.

On Windows, you will have to download and install git-flow. After installing git-flow, you can use it in your project by running git flow init.
```
$ git flow init
```
The git flow init command is an extension of the default git init command and does not change anything about your repository other than creating branches for you.

The general flow of Gitflow is as follows:

 1. A development branch is created from the master. 
 2. A publishing branch is created from the development branch. 
 3. Function branches are created from the development branch.
 4. When a function is complete, it is merged into the development branch.
 5. When the publishing branch is ready, it is merged into the development branch and the master. 
 6. If an issue is detected in the master, a remediation branch is created from    the master. 
 7. Once the proofing is complete, it is merged with both the   
    developmental and the master.



## Refereces
- Atlassian. 2021. _Flujo de trabajo de Gitflow | Atlassian Git Tutorial_. [online] Available at: <https://www.atlassian.com/es/git/tutorials/comparing-workflows/gitflow-workflow> [Accessed 21 April 2021].

- Chacon, S. and Straub, B., 2014. _Pro Git_. 2nd ed. [ebook] Available at: <https://git-scm.com/book/en/v2> [Accessed 21 April 2021].