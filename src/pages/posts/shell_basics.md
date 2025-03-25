# Shell Basics: A Beginner's Guide

The shell is a powerful command-line interface that allows users to interact with their operating system. Whether you're using Bash, Zsh, or Fish, understanding shell basics is essential for navigating and managing files efficiently.

## What is a Shell?

A shell is a command-line interpreter that takes user input, processes commands, and interacts with the operating system. Some common shells include:

- **Bash (Bourne Again Shell)** – Default on most Linux distributions.
- **Zsh (Z Shell)** – An extended version of Bash with better features.
- **Fish (Friendly Interactive Shell)** – A user-friendly shell with autosuggestions.

## Navigating the Shell

### Opening the Shell
- On Linux/macOS: Open a terminal (e.g., `Ctrl + Alt + T`).
- On Windows: Use Git Bash, WSL (Windows Subsystem for Linux), or PowerShell.

### Basic Commands
- `pwd` – Print the current working directory.
- `ls` – List files and directories.
- `cd <directory>` – Change directory.
- `mkdir <directory>` – Create a new directory.
- `rm <file>` – Remove a file.
- `rmdir <directory>` – Remove an empty directory.
- `cp <source> <destination>` – Copy files.
- `mv <source> <destination>` – Move or rename files.

## Working with Files

### Viewing Files
- `cat <file>` – Display file contents.
- `less <file>` – View large files interactively.
- `head <file>` – Show the first 10 lines.
- `tail <file>` – Show the last 10 lines.

### Editing Files
- Use `nano <file>` for simple editing.
- Use `vim <file>` for advanced editing.

## File Permissions

### Checking Permissions
```sh
ls -l <file>
```

### Changing Permissions
- `chmod +x <file>` – Make a file executable.
- `chmod 755 <file>` – Set read/write/execute permissions.

## Shell Scripting Basics

A shell script is a file containing a series of commands.

### Creating a Simple Script
```sh
#!/bin/bash
echo "Hello, World!"
```
Save the file as `script.sh`, then make it executable:
```sh
chmod +x script.sh
./script.sh
```

## Conclusion

Understanding shell basics enhances your efficiency and control over the operating system. Whether navigating directories, managing files, or writing scripts, mastering the shell is a valuable skill for any user.

