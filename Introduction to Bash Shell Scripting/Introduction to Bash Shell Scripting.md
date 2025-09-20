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

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/9d0d63339e4858fec5c4a614e495940fb283258d/Introduction%20to%20Bash%20Shell%20Scripting/Images/touch.png)

* To change the name of 'myBashScript' to 'muchBetterName', type `mv myBashScript muchBetter Name`
* You can check to see if it worked by typing `ls -l`

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/9d0d63339e4858fec5c4a614e495940fb283258d/Introduction%20to%20Bash%20Shell%20Scripting/Images/change%20name.png)

* You can delete the 'muchBetterName' file by using `rm muchBetterName`
* You can use `cat` on the command line to view the contents of any text file `cat kinglear.txt`

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/9d0d63339e4858fec5c4a614e495940fb283258d/Introduction%20to%20Bash%20Shell%20Scripting/Images/view%20file.png)

* To edit the file contents use `nano kinglear.txt`

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/9d0d63339e4858fec5c4a614e495940fb283258d/Introduction%20to%20Bash%20Shell%20Scripting/Images/edit%20file.png)

## Task 3: Finding Information
* To create a new directory called 'newDir' input `mkdir newDir`
* To change the name of the directory to 'backups' use `mv newDir backups`
* Use touch to create files in the backups directory: `touch backups/file1` `touch backups/file2`
* Use `ls -l backups` to look at what is in the backups directory

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/32c511c5cb8b105b6a2ff51f8c66f9c5428a0a6d/Introduction%20to%20Bash%20Shell%20Scripting/Images/backups%20directory.png)

* To delete the directory use `rm -ir backups`
* `-ir` is used for added protection since it will ask you if you want to delete the contents in the directory one by one

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/32c511c5cb8b105b6a2ff51f8c66f9c5428a0a6d/Introduction%20to%20Bash%20Shell%20Scripting/Images/delete%20backups.png)

* Create two new directories and add a file in the directory:
  * `mkdir newDir`
  * `mkdir newDir/backups`
  * `touch newDir/backups/cleanbackup`
* Then go to the root directory to find the file with 'backup' in the name that appears somwhere in the user directory: `find / -name "*backup*" 2>dev/null | grep $USER`
* `2>/dev/null` tells the shell to take error input and redirect it to `/dev/null` where it's deleted
* Grep tells the shell to look for a regular expression

![alt text](https://github.com/Nathan-Reynolds09/Cybersecurity-Portfolio/blob/32c511c5cb8b105b6a2ff51f8c66f9c5428a0a6d/Introduction%20to%20Bash%20Shell%20Scripting/Images/find%20file.png)

## Task 4: Aliases

