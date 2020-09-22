**The Shell** - a program that takes your commands from the keyboard and sends them to the operating system to perform

Almost all Linux distributions will default to the bash (Bourne Again Shell) shell. There are other shells available such as ksh (korn shell), zsh (Z shell), tsch(tee-see shell)

Different shells will have different prompts, in our case the $ is for a normal user using Bash, Bourne or Korn shell, you don't add the prompt symbol when you type the command, just know that it's there

### Basic Commands

- `$echo` - display a line of text i.e Echo the STRING(s) to standard output.

- `$date` - Display the current time in the given FORMAT, or set the system date.

- `$whoami` - Print  the  user  name  associated  with the current effective user ID

- `$pwd` - Print the full filename of the current working directory.
  * Everything in Linux is a file. 
  * Every file is organized in a hierarchical directory tree. The first directory in the filesystem is aptly named the root directory. 
  * The root directory has many folders and files which you can store more folders and files. The location of these files and directories are referred to as paths.
  * Navigation of the filesystem is helpful if you know where you are and where you are going. To see where you are, you can use the pwd command, this command means “print working directory” and it just shows you which directory you are in.
  * *note the path stems from the root directory*

- `$cd` - Change the shell working directory. Syntax is `$cd [dir]`  This changes the current directory to DIR.  The default DIR is the value of the HOME shell variable.
  * To move around the filesystem a bit, we’ll need to navigate our way using paths
  * There are two different ways to specify a path:
     * Absolute path: This is the path from the root directory. The root directory is commonly shown as a slash. Every time your path starts with / it means you are starting from the root directory.
     * Relative path: This is the path from where you are currently in filesystem.
It can get pretty tiring navigating with absolute and relative paths all the time, luckily there are some shortcuts to help you out.

  * `$cd .` (current directory). This is the directory you are currently in.
  * `$cd ..` (parent directory). Takes you to the directory above your current.
  * `$cd ~` (home directory). This directory defaults to your “home directory”. Same as `$cd` without any flags
  * `$cd -` (previous directory). This will take you to the previous directory you were just at.

- `$ls` - list directory contents (the current directory by default). The ls command will list directories and files in the current directory by default, however you can specify which path you want to list the directories of by typing it after the ls command
Some useful flags to use with `$ls` command:
  * `$ls -a` - list all files including hidden files (files that begin with a period (.)) 
  * `$ls -l` - shows a detailed list of files in a long format. This will show you detailed information, starting from the left: file permissions, number of links, owner name, owner group, file size, timestamp of last modification, and file/directory name
  * `ls -R` - recursively list directory contents
  * `ls -r` - reverse order while sorting. Entries sorted alphabetically by default
  * `ls -t` - sort by modification time, newest first

**Note : Commands have things called flags (or arguments or options, whatever you want to call it) to add more functionality. See how we added -a and -l, well you can add them both together with -la. The order of the flags determines which order it goes in, most of the time this doesn’t really matter so you can also do ls -al and it would still work**

- `$touch` - allows you to the create new empty files. Also used to change timestamps on existing files and directories

- `$file` - determine file type. file tests each argument in an attempt to classify it. There are three sets of tests, performed in this order: filesystem tests, magic tests, and language tests. The first test that succeeds causes the file type to be printed.

    