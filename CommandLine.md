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

# Compare

| Command | Description                                                  |
| ------- | ------------------------------------------------------------ |
| wc      | Allows you to count the number of lines, words, characters, and bytes of each given file or standard input and print the result |
```
$ wc *.md
  184   588  3741 CommandLine.md
  376  1827 13707 GitCodes.md
    2     8    32 README.md
  562  2423 17480 total
```

# Find files, folders and inside files
| Command                    | Description                              |
| -------------------------- | ---------------------------------------- |
| find  /dir/  -name  "name" | Find files starting with "name" in "dir" |

```
$ find . -name '*txt'
```
Next, a list of all files ending in .txt is displayed, even those found in other directories

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

| Command    | Description                                                  |
| ---------- | ------------------------------------------------------------ |
| systeminfo | Displays the specific properties and settings of the computer. |
| uname      | print system information                                     |
| lshw tool  | gather vast information about your hardware components such as cpu, disks, memory, usb controllers etc. |

```
$ systeminfo

Nombre de host:                            LAPTOP-XXXXX
Nombre del sistema operativo:              Microsoft Windows 10 Home Single Language
Versión del sistema operativo:            XXXXXXXXXXXXXX
Fabricante del sistema operativo:          XXXX
Configuración del sistema operativo:       XXXX
Tipo de compilación del sistema operativo: XXXX
Propiedad de:                              XXXX
Organización registrada:                   XXXX
Id. del producto:                          XXXX
Fecha de instalación original:             XXXX
Tiempo de arranque del sistema:            XXXX
Fabricante del sistema:                    XXXX
Modelo el sistema:                         XXXX
Tipo de sistema:                           XXXX
```

```
$ uname

Linux

$ sudo lshw

tecmint.com               
    description: Notebook
    product: XXX
    vendor: LENOVO
    version: Lenovo
    serial: XXXXX
    width: 64 bits
    capabilities: XXX
```

## References
- Shaw, Z., 2011. _The CLI Crash Course: Controlling Your Computer With The Terminal_.
- Kili, A., 2021. _10 Useful Commands to Collect System and Hardware Information in Linux_. [online] Tecmint.com. Available at: <https://www.tecmint.com/commands-to-collect-system-and-hardware-information-in-linux/#:~:text=1.,kernel%20name%20of%20your%20system.&text=To%20view%20your%20network%20hostname,with%20uname%20command%20as%20shown.> [Accessed 21 April 2021].