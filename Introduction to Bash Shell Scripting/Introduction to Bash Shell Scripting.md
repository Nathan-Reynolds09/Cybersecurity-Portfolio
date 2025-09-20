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

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/d2b8157d8564ace4907ffc71f9562baf5d57902f/Introduction%20to%20Bash%20Shell%20Scripting/Images/echo%20shell.png)

* To see what files and directories are available, input `ls` into the terminal
* This will list visible files in the directory you are currently in

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/d2b8157d8564ace4907ffc71f9562baf5d57902f/Introduction%20to%20Bash%20Shell%20Scripting/Images/ls.png)

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

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/d2b8157d8564ace4907ffc71f9562baf5d57902f/Introduction%20to%20Bash%20Shell%20Scripting/Images/ls%20-al.png)
  
* Type `cd /` to get to your root directory
* You can type `ls -l` to see what is in this directory
* Then you can input `cd` to change directory and then input `pwd` to show that you are back in your user directory

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/d2b8157d8564ace4907ffc71f9562baf5d57902f/Introduction%20to%20Bash%20Shell%20Scripting/Images/cd%201.png)
![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/d2b8157d8564ace4907ffc71f9562baf5d57902f/Introduction%20to%20Bash%20Shell%20Scripting/Images/cd%202.png)

* To go up one directory, type `cd ..` In this case we go to /home.
* Another way to go back to your user directory is by using `cd coder`

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/d2b8157d8564ace4907ffc71f9562baf5d57902f/Introduction%20to%20Bash%20Shell%20Scripting/Images/cd%20...png)

## Task 2: Manipulating Files
* To create a file called 'myBashScript', input `touch myBashScript`
* To make sure the file is there you can type `ls -l myBashScript`

![alt text](touch image)

* To change the name of 'myBashScript' to 'muchBetterName', type `mv myBashScript muchBetter Name`
* You can check to see if it worked by typing `ls -l`

![alt text](change name image)

* You can delete the 'muchBetterName' file by using `rm muchBetterName`
* You can use `cat` on the command line to view the contents of any text file `cat kinglear.txt`

![alt text](view file image)

* To edit the file contents use `nano kinglear.txt`

![alt text](edit file image)

## Task 3: Finding Information
