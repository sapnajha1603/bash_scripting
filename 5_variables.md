Variables in Linux are used to store and manipulate data in shell scripts or the command line. They act as placeholders for values such as strings, numbers, or paths, making scripts more dynamic and reusable.
Types of Variables in Linux:

    Environment Variables: System-wide variables that affect the environment of processes and shells. Examples:
        $HOME - The current user's home directory.
        $PATH - Directories the shell searches for executable files.
        $USER - The name of the logged-in user.

    Shell Variables: Variables specific to the shell session, often set by the user or script. Examples:
        my_var="Hello" - A user-defined variable.
        $BASH_VERSION - The current shell's version.

    Positional Parameters: Special variables for script arguments. Examples:
        $1, $2, ... - The first, second, etc., arguments passed to the script.
        $@, $* - All script arguments.

    Special Variables:
        $? - Exit status of the last command.
        $$ - The process ID of the current shell.
        $# - The number of arguments passed to the script.

Example of Using Variables:

#!/bin/bash
name="Sampreeth"
echo "Hello, $name!"  # Outputs: Hello, Sampreeth!

Key Points:

    Variables do not require a data type declaration (they are untyped).
    To reference a variable, use the $ symbol before its name.
    Use export to make a shell variable an environment variable accessible by child processes:

    export var="value"

Variables are essential in Linux for customizing environments and writing dynamic, reusable scripts.