## Introduction to Bash Shell Scripting

In this project I will learn several Bash shell commands that will allow me to navigate and use the shell for everyday tasks. The project objectives are:
* Navigating file directories
* Viewing, editing, creating, deleting, and renaming files on the command line and with text editing tools
* Finding information about files, logs, command history, and file paths
* Editing user aliases to personalize the environment
* Creating a script to back up the user directory
* Automating scripts with cron

## Task 1: Navigation
* To find out what shell is running, you can input `echo $SHELL` into the terminal
* Echo means print and the string shell is the variable that refrences the shell
* The terminal returns the path to the shell in use, which for this case it's bash

![alt text](echo shell image)

* To see what files and directories are available, input `ls` into the terminal
* This will list visible files in the directory you are currently in

![alt text](ls image)

* You can use options on commands to expand how that command functions, for example `ls -al`
* `ls` is the command and `-al` is the option
* The dash tells the command that an option is starting, the 'a' stands for all, and the 'l' stands for long listing format
* The first column says what it is and what its permissions are. If it starts with a dash, it's a file. If there's a 'd', it's a directory.
* The series of r's, w's, x's, and dashes after defines:
  * who has what kind of access to that file or directory
  * who can read, write, and execute
* The two columns that say 'coder' are the users and the groups
* The next column tells you the files size in bytes, then the date it was last accessed
* The final column states the file or directory name

![alt text](ls -al image)
  
* Type `cd /` to get to your root directory
* You can type `ls -l` to see what is in this directory
* Then you can input `cd` to change directory and then input `pwd` to show that you are back in your user directory

![alt text](cd 1 image)
![alt text](cd 2 image)

* To go up one directory, type `cd ..` In this case we go to /home.
* Another way to go back to your user directory is by using `cd coder`

![alt text](cd .. image)
