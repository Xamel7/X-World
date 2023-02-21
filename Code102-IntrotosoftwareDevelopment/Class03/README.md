## Initial Customization

# Configuration of Variables
>An inherent Git tool called git config allows the setting of configuration variables that control aspects of Git’s operation and look.

# Identity Setting

>After installing Git, users should immediately set the user name and email address, which will be used for every Git commit.

# Default Text Editor

>Without configuration of a default text editor, Git will use the system’s default editor–most likely Vim. To configure a different text editor, such as Emacs, type the following into your Terminal or Command Line:$ git config --global core.editor emacs

# Check Settings

>To check settings, use the git config --list command.

# Cloning

>By cloning the file, you have copied all versions of all files for a project. This command leads to the creation of a directory called “test,” with an initialized .git directory inside it, which has copies of all versions of all files for the specified project.

# Checked File Status

>Utilize the command *git status*

# Tracking and staging
>*Single File*
git add filename
>*All Files*
$ git add *

## Committing a File

>After staging one or multiple files, you should commit the changes and record what you did within the commit message:
> $ git commit -m "made change x,y,z"

## Committing All Changes

> $ git commit -a

## Seeing your remotes

By running the git remote command, you can view the short names, such as “origin,” of all specified remote handles.

By using git remote -v, you can view all the remote URLs next to their corresponding short names.
