# Create and Delete Directories

## Create a directory (mkdir)

| Command | Description      |
| ------- | ---------------- |
| mkdir   | Make a directory |

These are all the different ways you can run mkdir.
 ```
$ mkdir DirectoryName
$ mkdir DirectoryName1/DirectoryName2
 ```
In the first example a single directory is created and in the second example a directory is created inside another directory
## Remove Directory (rmdir)
| Command | Description         |
| ------- | ------------------- |
| rmdir   | remove a  directory |
 ```
C:\User\Example\DirectoryName
$ cd..

C:\User\Example
$ ls
file1.txt DirectoryName/

C:\User\Example
$ rmdir DirectoryName

C:\User\Example
$ ls
file1.txt
 ```
As you can see in the example before applying the command the directory appears but after applying it we can see that it is no longer found
# Navigate
## Show files
| Command | Description |
| ------- | ----------- |
| ls      | List files  |
```
C:\User\Example
$ ls
file1.txt DirectoryName1/

C:\User\Example
$ ls *.txt
file1.txt 
```
The directories with the ending "/" and the files with their respective extension are shown.

## Change Directory (cd)
| Command | Description       |
| ------- | ----------------- |
| cd      | Change directory  |
| cd..    | Go up a directory |
 ```
C:\User\Example
$ cd DirectoryName1

C:\User\Example\DirectoryName1
$ cd DirectoryName2

C:\User\Example\DirectoryName1\DirectoryName2
$ cd..

C:\User\Example\DirectoryName1
$ cd..

C:\User\Example
 ```
With this command we can move freely between the directories

## Pushd ??

# Compare
# Find files, folders and inside files
## Finding Files (find)
| Command                   | Description                              |
| ------------------------- | ---------------------------------------- |
| find  /dir/  -name  name* | Find files starting with "name" in "dir" |

```
C:\User\Example
$ ls
DirectoryName1/

C:\User\Example
$ touch file1.txt
 
C:\User\Example
$ ls
file1.txt DirectoryName1/
```
# Create and edit text files
## Create empty file (touch)
| Command | Description |
| ------- | ----------- |
| touch   | Create file |

```
C:\User\Example
$ ls
DirectoryName1/

C:\User\Example
$ touch file1.txt
 
C:\User\Example
$ ls
file1.txt DirectoryName1/
```
We can see that after applying the command an empty text file is created
## Remove file (rm)
| Command | Description |
| ------- | ----------- |
| rm      | Remove file |

```
C:\User\Example
$ ls
file1.txt DirectoryName1/

C:\User\Example
$ rm file1.txt

C:\User\Example
$ ls
DirectoryName1/
```
Contrary to the previous example, we can see that the file disappears after applying the command
## Copy a file (cp)
| Command | Description |
| ------- | ----------- |
| cp      | copy a file |

```
C:\User\Example
$ ls
file1.txt DirectoryName1/

C:\User\Example
$ cp file1.txt file2.txt

C:\User\Example
$ ls
file1.txt file2.txt DirectoryName/

C:\User\Example
$ cp file1.txt DirectoryName/

C:\User\Example
$ cd DirectoryName

C:\User\Example\DirectoryName
$ ls
file1.txt
```
In this example we can see how to copy a file to another file and also how to copy a file to another directory.

## Edit a text file (nano)
| Command | Description      |
| ------- | ---------------- |
| nano    | Edit a text file |

```
C:\User\Example
$ nano file1.txt
```
A text editor will open where you can edit the file, to exit that editor press Ctrl + X

## Stream A File (cat)
| Command | Description                  |
| ------- | ---------------------------- |
| cat     | Stream the content of a file |

```
C:\User\Example
$ cat file1.txt

This is a title
This is a text 
```
A text editor will open where you can edit the file, to exit that editor press Ctrl + X

# Get the state of the computer