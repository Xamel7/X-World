# [Class02](./Class02/)

>A command line, or terminal, is a text based interface to the system. You are able to enter commands by typing them on the keyboard and feedback will be given to you similarly as text.

## What are they

## Example

>Line 1-presents us with a prompt ( user@bash ). After that we entered a command ( ls ). Typically a command is always the first thing you type. After that we have what are referred to as command line arguments ( -l /home/ryan ). Important to note, these are separated by spaces (there must be a space between the command and the first command line argument also). The first command line argument ( -l ) is also referred to as an option. Options are typically used to modify the behaviour of the command. Options are usually listed before other arguments and typically start with a dash ( - ).
Lines 2 - 5-are output from running the command. Most commands produce output and it will be listed straight under the issuing of the command. Other commands just perform their task and don't display any information unless there was an error.
Line 6-presents us with a prompt again. After the command has run and the terminal is ready for you to enter another command the prompt will be displayed. If no prompt is displayed then the command may still be running (you will learn later how to deal with this).
Your terminal probably won't have line numbers on it. I have just included them here to make it easier to refer to different parts of the material.

## Opening a Terminal

>If you are on Windows and intend to remotely log into another machine then you will need an SSH client. A rather good one is Putty (free)

## The Shell,Bash

Bash which stands for Bourne again shell. 
If you would like to know which shell you are using you may use a command called echo to display a system variable stating your current shell. echo is a command which is used to display messages.

## Beginner level Navigation

>The first command we are going to learn is *pwd* which stands for Print Working Directory. 

## What's in our current position?

It's one thing to know where we are. Next we'll want to know what is there. The command for this task is ls. It's short for list. Let's give it a go.

## Example

Line 1 - We ran ls in it's most basic form. It listed the contents of our current directory.
Line 4 - We ran ls with a single command line option ( -l ) which indicates we are going to do a long listing. A long listing has the following:
First character indicates whether it is a normal file ( - ) or directory ( d )
Next 9 characters are permissions for the file or directory (we'll learn more about them in section 6).
The next field is the number of blocks (don't worry too much about this).
The next field is the owner of the file or directory (ryan in this case).
The next field is the group the file or directory belongs to (users in this case).
Following this is the file size.
Next up is the file modification time.
Finally we have the actual name of the file or directory.
Line 10 - We ran ls with a command line argument ( /etc ). When we do this it tells ls not to list our current directory but instead to list that directories contents.
Line 13 - We ran ls with both a command line option and argument. As such it did a long listing of the directory /etc.
Lines 12 and 18 just indicate that I have cut out some of the commands normal output for brevities sake. When you run the commands you will see a longer listing of files and directories.


## Paths

>Whenever we refer to either a file or directory on the command line, we are in fact referring to a path. ie. A path is a means to get to a particular file or directory on the system.

#Absolute and Relative Paths

>There are 2 types of paths we can use, absolute and relative. Whenever we refer to a file or directory we are using one of these paths.

>At the very top of the structure is what's called the root directory. It is denoted by a single slash ( / ). It has subdirectories, they have subdirectories and so on. Files may reside in any of these directories.

>Absolute paths-specify a location (file or directory) in relation to the root directory. You can identify them easily as they always begin with a forward slash ( / )

>Relative paths-specify a location (file or directory) in relation to where we currently are in the system. They will not begin with a slash.

## Example

Line 1 - We ran pwd just to verify where we currently are.
Line 4 - We ran ls providing it with a relative path. Documents is a directory in our current location. This command could produce different results depending on where we are. If we had another user on the system, bob, and we ran the command when in their home directory then we would list the contents of their Documents directory instead.
Line 7 - We ran ls providing it with an absolute path. This command will provide the same output regardless of our current location when we run it.

## More about paths

~ (tilde) - This is a shortcut for your home directory. eg, if your home directory is /home/ryan then you could refer to the directory Documents with the path /home/ryan/Documents or ~/Documents
. (dot) - This is a reference to your current directory. eg in the example above we referred to Documents on line 4 with a relative path. It could also be written as ./Documents (Normally this extra bit is not required but in later sections we will see where it comes in handy).
.. (dotdot)- This is a reference to the parent directory. You can use this several times in a path to keep going up the hierarchy. eg if you were in the path /home/ryan you could run the command ls ../../ and this would do a listing of the root directory.

In order to move around in the system we use a command called cd which stands for change directory. 

cd [location]

If you run the command cd without any arguments then it will always take you back to your home directory.

The command cd may be run without a location as we saw in the shortcut above but usually will be run with a single command line argument which is the location we would like to change into. The location is specified as a path and as such may be specified as either an absolute or relative path and using any of the path building blocks mentioned above.

## Everything is a file

>A text file is a file, a directory is a file, your keyboard is a file (one that the system reads from only), your monitor is a file (one that the system writes to only) etc. 

## Linux is an Extensionless System

 A file extension is normally a set of 2 - 4 characters after a full stop at the end of a file, which denotes what type of file it is. The following are common extensions:

file.exe - an executable file, or program.
file.txt - a plain text file.
file.png, file.gif, file.jpg - an image.

file
obtain information about what type of file a file or directory is.
ls -a
List the contents of a directory, including hidden files.

Everything is a file under Linux
Even directories.
Linux is an extensionless system
Files can have any extension they like or none at all.
Linux is case sensitive
Beware of silly typos.