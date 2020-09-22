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

- `$cat` - concatenate files and print on the standard output. With no FILE, or when FILE is -, read standard input.
It’s not great for viewing large files and it’s only meant for short content.

- `$less` - for viewing text files larger than a simple output. Less  does  not  have to read the entire input file before starting, so with large input files it starts up faster than text editors  like vi.
The text is displayed in a paged manner, so you can navigate through a text file page by page
Once you’re in the less command, you can actually use other keyboard commands to navigate in the file:
  * `q` - Used to quit out of less and go back to your shell.
  * `Page up, Page down, Up and Down` - Navigate using the arrow keys and page keys.
  * `g` - Moves to beginning of the text file.
  * `G` - Moves to the end of the text file.
  * `/pattern` - Search forward for (N-th) matching line.
  * `?pattern` - Search backward for (N-th) matching line.
  * `h` - If you need a little help about how to use less while you’re in less, use help.

- `$history` - Many programs read input from the user a line at a time. The GNU History library is able to keep track of those lines, associate arbitrary data with each line, and utilize information  from  previous  lines  in composing new ones.
When you run the history, it displays a numbered list of all the commands you have run and the last command will always be history because it is the one you have run last
  * *Want to run the same command you did before, just hit the up arrow.*
  * *`!!` - run the previous command without typing it again*
  * *`ctrl-R` - The reverse search command, if you hit ctrl-R and you start typing parts of the command you want it will show you matches and you can just navigate through them by hitting the ctrl-R key again. Once you found the command you want to use again, just hit the Enter key*
  * *`$ clear` or `ctrl+l` - clears up your display*
  * *tab completion - If you start typing the beginning of a command, file, directory, etc and hit the Tab key, it will autocomplete based on what it finds in the directory you are searching as long as you don’t have any other files that start with those letters*

- `$cp [OPTIONS]... SOURCE DEST` - copy files and directories. Copy SOURCE to DEST, or multiple SOURCE(s) to DIRECTORY.
You can copy multiple files and directories as well as use wildcards. A wildcard is a character that can be substituted for a pattern based selection, giving you more flexibility with searches. You can use wildcards in every command for more flexibility
  - `*` the wildcard of wildcards, it's used to represent all single characters or any string.
  - `?` used to represent one character
  - `[]` used to represent any character within the brackets
  * Some useful flags (OPTIONS) to use with `cp` command
    * `-r` - this will recursively copy the files and directories within a directory.
    * `-i` - (interactive) to prompt you before overwriting a file. This is because if you copy a file over to a directory that has the same filename, the file will be overwritten with whatever you are copying over.

- `$mv [OPTION]...SOURCE DEST` - move (rename) files. Rename SOURCE to DEST, or move SOURCE(s) to DEST 
  * Some useful flags (OPTIONS) to use with `mv` command
    * `-i` - (interactive) to prompt you before overwriting a file. This is because if you move a file over to a directory that has the same filename, the file will be overwritten with whatever you are moving over.
    * `-b` - make a backup of each existing destination file (one that is overwritten) and it will just rename the old version with a `~` at the end

- `$mkdir [OPTION]... DIRECTORY...` - make directories. Create the DIRECTORY(ies), if they do not already exist.
  * `-p` (parent flag) - create subdirectories at the same time.

- `$rm [OPTION]... [FILE]...` - remove files or directories. rm removes each specified file. By default, it does not remove directories.
  * Take caution when using rm, there is no magical trash can that you can fish out removed files. Once they are gone, they are gone for good, so be careful.
  * Write-protected files will prompt you for confirmation before deleting them. If a directory is write-protected it will also not be easily removed.
  * Some useful flags (OPTIONS) for the `rm` command:
    * `&rm -f` - -f or force option tells rm to remove all files, whether they are write protected or not, without prompting the user (as long as you have the appropriate permissions).
    * `$rm -i` - interactive. give you a prompt on whether you want to actually remove the files or directories
    * `$rm -r` -  (recursive) to remove all the files and any subdirectories it may have. You can’t just rm a directory by default, you’ll need to add the -r flag 
    * ***You can also remove a directory with the `rmdir` command. (fails if directory is not empty)***
    