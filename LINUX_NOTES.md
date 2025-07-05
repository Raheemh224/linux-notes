### Linux Notes – DevOps Bootcamp
# Basic Commands
`whoami` — Shows the current logged-in user.

`pwd` — Prints the current working directory.

`ls` — Lists files and directories.

`find` / -name "found.txt" — Searches the entire system for a file named "found.txt".

Temporary Files
/tmp — Directory for temporary files.

# What Are Commands?
- Text instructions that tell the OS what to do.

- Entered directly in the terminal.

- Commands are case sensitive.

- Can have options and arguments to modify behaviour.

Manuals (man) provide detailed instructions.

# Shells
Use echo $SHELL to see your current shell.

`cat /etc/shells` lists all available shells on your system.

apt-get is a package manager to install software.

# Installing and Setting Up ZSH
- Install ZSH:

`sudo apt-get install zsh`

- Set ZSH as your default shell:

`sudo chsh -s /bin/zsh`

- If that doesn't work, try:

`sudo chsh -s $(which zsh) $(whoami)`

Restart the terminal to start using ZSH.

ZSH Configuration
.zshrc is a hidden configuration file in your home directory.

To apply changes made to .zshrc:

`source ~/.zshrc`

To configure the Powerlevel10k theme:

p10k configure

Plugins
Plugins extend the shell’s features, such as auto-completion.

# Linux File System
Root directory is /.

Important directories:

- /boot — Boot files and kernel.

- /dev — Device files (e.g., disks).

- /etc — System-wide configuration files and startup scripts.

- /tmp — Temporary files.

# Common Commands for Files and Directories
Command	Description
`pwd`	Print working directory.
`cd`	Change directory.
`ls`	List files and directories.
`mkdir`	Create a new directory.
`rmdir`	Remove an empty directory.
`touch`	Create an empty file or update timestamps.
`rm`	Remove a file. Use rm -r for directories.
`cat`	Display file contents.
`echo` "text" > file	Write (overwrite) text to a file.
`echo `"text" >> file	Append text to a file.
`grep`	Search for text within files.

`ls -a` shows hidden files (starting with .).

`cd ..` moves to the parent directory.

- Handling Spaces in File and Directory Names
Use quotes or backslashes to include spaces:

`touch "my project"`
`touch my\ project`

# Vim Text Editor Basics
Modes: Command, Insert, Visual.

- Navigation: h left, j down, k up, l right.

- Delete line: dd

- Copy (yank): yy

- Paste: p

- Undo: u

- Redo: Ctrl + r

- Search: /word then n for next occurrence.

User and Group Management
Create a user:

`sudo useradd newuser`

Switch user:

`su newuser`

Add user to sudo group:

`sudo usermod -aG sudo newuser`

Create a group:

`sudo groupadd newgroup`

Add user to group:

`sudo usermod -aG newgroup newuser`

# File Permissions and Ownership
Permissions format: rwx:rwx:rwx (User : Group : Others).

r = read, w = write, x = execute.

Change permissions:

- chmod ug=rw,o=r file.txt

Change owner:

- sudo chown newuser file.txt

Change owner and group:

- sudo chown newuser:newgroup file.txt
