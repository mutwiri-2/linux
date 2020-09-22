Processes use I/O streams to receive input and return output e.g By default the echo command takes the input (standard input or stdin) from the keyboard and returns the output (standard output or stdout) to the screen. So that's why when you type echo Hello World in your shell, you get Hello World on the screen. However, I/O redirection allows us to change this default behavior giving us greater file flexibility.

- `>` - is a redirection operator that allows us to change where standard output goes.  It allows us to send the output of echo Hello World to a file instead of the screen.  If the file does not already exist it will create it for us. However, if it does exist it will overwrite it (you can add a shell flag to prevent this depending on what shell you are using)
- `>>` - is a redirection operator that appends content to the end of the file instead of overwriting it, if the file doesn't already exist it will create it for us like it did with the `>` redirector!

We have different stdout streams we can use, such as a file or the screen. There are also different standard input (stdin) streams we can use as well like the keyboard , we can also use files, output from other processes and the terminal as well.

- `<` - for stdin redirection. It is a redirection operator that allows us to change where standard input comes from.