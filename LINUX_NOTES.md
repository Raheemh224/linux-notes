# Linux Essentials – DevOps Bootcamp Notes

These are my beginner-friendly notes from the Linux module of my DevOps Bootcamp. They cover core Linux commands, shell basics, file management, user permissions, and more.

---

## Basic Linux Commands

| Command        | Description                                                  |
|----------------|--------------------------------------------------------------|
| `whoami`       | Shows the current logged-in user.                            |
| `pwd`          | Prints the current working directory.                        |
| `ls`           | Lists files and directories. Use `ls -a` to include hidden files. |
| `cd`           | Changes directory. Use `cd ..` to go up one level.          |
| `mkdir <name>` | Creates a new directory.                                     |
| `rmdir <name>` | Removes an empty directory.                                  |
| `touch <file>` | Creates a new empty file.                                    |
| `rm <file>`    | Deletes a file. Use `rm -r <dir>` to delete directories and their contents. |
| `cat <file>`   | Displays the content of a file.                              |
| `echo "text" > file.txt` | Writes text to a file (overwrites content).             |
| `echo "text" >> file.txt` | Appends text to a file without deleting existing content. |
| `grep <word> <file>` | Searches for a word in a file.                              |
| `find / -name "filename"` | Searches for a file by name starting from root (`/`).      |

---

## Understanding the Shell

### What is a Shell?

A **shell** is a program that acts as a bridge between the user and the operating system. It takes commands you type and translates them into actions the OS can perform.

- Common shell: **Bash** (Bourne Again Shell)  
- Another popular shell: **ZSH**

### Check Current Shell

```bash
echo $SHELL
View Available Shells
bash
Copy code
cat /etc/shells
Installing and Setting Up ZSH
ZSH is a powerful alternative to Bash with advanced features like autocomplete, spelling correction, and themes.

Install ZSH
bash
Copy code
sudo apt-get install zsh
Set ZSH as Default Shell
bash
Copy code
sudo chsh -s /bin/zsh
If that doesn't work, try:

bash
Copy code
sudo chsh -s $(which zsh) $(whoami)
$(which zsh) locates the ZSH binary.

$(whoami) applies it to your current user.

Restart to Apply Changes
ZSH Configuration
ZSHRC File
.zshrc is the configuration file for ZSH located in your home directory (~).

To reload changes:

bash
Copy code
source ~/.zshrc
Plugins & Themes
Plugins enhance the shell with features like syntax highlighting and autosuggestions.

Popular Framework: Oh My ZSH

Manages ZSH configurations.

Comes with themes, plugins, and customisation options.

Powerlevel10k Theme
To configure it:

bash
Copy code
p10k configure
Themes are stored here:

bash
Copy code
cd ~/.oh-my-zsh/themes
ls
Linux File System Overview
The file system starts from the root directory / and branches into:

Directory	Description
/	Root directory (top of the hierarchy)
/boot	Boot loader files and Linux kernel
/dev	Device files (e.g., disks, USBs)
/etc	System-wide config files and startup scripts
/tmp	Temporary files
/home	User directories

File Management Commands
Copy, Move & Delete
bash
Copy code
cp file.txt /path/       # Copy a file
cp -r dir1/ dir2/        # Copy a directory recursively
mv old.txt new.txt       # Rename or move a file
rm file.txt              # Delete a file
rm -r dir/               # Delete a directory and its contents recursively
Creating Nested Directories
bash
Copy code
mkdir -p project/src/components
Handling Spaces in File/Folder Names
bash
Copy code
touch "my project.txt"
# or
touch my\ project.txt
Working with Files
Command	Description
touch file.txt	Creates an empty file
cat file.txt	Displays contents of the file
echo "text" > file.txt	Writes text to a file (overwrites)
>>	Appends text to a file
head file.txt	Shows first 10 lines of a file
tail file.txt	Shows last 10 lines of a file
head -n 10 file.txt | tail -n 5	Shows lines 6 to 10 (combining head & tail)

VIM Basics (Text Editor)
VIM has 3 modes: Command, Insert, and Visual.

Action	Command
Enter insert mode	i
Save and exit	:wq
Quit without saving	:q!
Delete line	dd
Copy (yank)	yy
Paste	p
Undo	u
Redo	Ctrl + r
Search	/word
Next result	n
Previous result	N
Move cursor	h j k l

Users and Permissions
Users
bash
Copy code
sudo useradd newuser
su newuser                    # Switch user
sudo usermod -aG sudo newuser # Give sudo privileges
Groups
bash
Copy code
sudo groupadd newgroup
sudo usermod -aG newgroup newuser
sudo groupdel newgroup
To add a user to multiple groups:

bash
Copy code
sudo usermod -aG admin,admin2 newuser
File Permissions & Ownership
Permission Symbols
r = read

w = write

x = execute

Format: rwx:rwx:rwx (User : Group : Others)

Change Permissions
bash
Copy code
chmod ug=rw, o=r file.txt
Change Ownership
bash
Copy code
sudo chown newuser file.txt           #