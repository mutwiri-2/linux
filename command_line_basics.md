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