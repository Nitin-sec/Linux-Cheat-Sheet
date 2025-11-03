# Linux Commands — (My notes)

## File & Directory
- `pwd` — to see where we are
- `ls` — to see surrounding
- 'ls -a' - for viewing hidden files
- 'ls -l' - for detailed info
- 'ls -r' - sorts in reverse order
- 'ls -la' - combined command flags
- `cd <path>` / `cd ..` — change directory / go back
- 'cd .' - represent the directory we are currently in
- 'cd -' - takes back to the last directory we were in
- 'cd ~' - shortcut to personal home directory
- `mkdir <dir>` — make directories
- `rmdir <dir>` — remove directories
- `touch <file>` — creates an empty file. If used on already existing file, then it updates the timestamp of the file.
- 'file' - to find the file type

## Edit / View Files
- `mousepad <file>` — GUI editor to write or change files
- 'touch -r <file1> <file2>' / 'touch -d <tiem> <filename>' - used to match the timestamp of two given files. / used to give specific timestamp.
- `nano <file>` — terminal editor to create/edit files
- `cat <file>` — view, create, concatenate, copy text files
- `truncate -s 0 <file>` — remove file content (empty file)
- `echo "text"` — print text to terminal or redirect into files

## File Ops
- `rm <file>` — delete a file. Forceful Deletion with -f

To bypass these safety prompts and remove files unconditionally, you can use the force option.

rm -f file1

The -f (force) option tells rm to remove all specified files without prompting, even if they are write-protected (assuming you have the necessary permissions). This option is a key part of the rm -rf linux command and should be used with great care.
Interactive Deletion with -i

For a safer approach, use the interactive flag. This is a highly recommended practice when working with the rm linux command.

rm -i file

The -i (interactive) flag prompts you for confirmation before deleting each file, helping to prevent accidental removal.
Removing Directories

By default, rm cannot delete a directory. To do so, you must use the recursive option.

rm -r directory

The -r (recursive) flag instructs rm to delete a directory and all of its contents, including any subdirectories and files. This is the "r" in the linux rm -rf command.
Using rmdir for Empty Directories

As a safer alternative, you can remove an empty directory with the rmdir command.

rmdir directory
- `cp <src> <dst>` — copy file or directory.  Using Wildcards for Bulk Copying

Wildcards are special characters that help you select multiple files based on patterns, providing great flexibility.

    *: Matches any sequence of characters.
    ?: Matches any single character.
    []: Matches any one of the characters enclosed in the brackets.

For example, to copy all JPEG images from your current location to the Pictures directory:

cp *.jpg /home/pete/Pictures

Copying Directories Recursively

If you try to copy a directory using cp without any options, you will receive an error. To copy a directory and all of its contents, including subdirectories, you must use the -r (recursive) flag.

cp -r Pumpkin/ /home/pete/Documents

This command copies the Pumpkin directory and everything inside it to your Documents directory.
Handling File Overwrites

By default, cp will overwrite a file at the destination if it has the same name. To prevent accidental data loss, use the -i (interactive) flag, which prompts for confirmation before overwriting.

cp -i mycoolfile /home/pete/Pictures

Conversely, if you want to force an overwrite without any prompts, you can use the cp -f flag. This is useful in scripts where user interaction is not possible.

cp -f mycoolfile /home/pete/Pictures

Preserving File Attributes with cp -p

When you copy a file, its metadata, such as modification time and ownership, is typically updated. To preserve these original attributes, the cp -p flag is essential. Using cp -p in linux ensures that the copy is an exact replica, not just in content but also in its metadata.

The cp -p flag is particularly useful for backups or when migrating files where preserving timestamps is critical.

cp -p mycoolfile /home/pete/backups/

This command demonstrates how to use linux cp -p to copy mycoolfile while preserving its mode, ownership, and timestam
- `mv <src> <dst>` — move / rename (cut & paste).  A useful option for this is linux mv -t, which allows you to specify the target directory first. This can be clearer when moving many files.

mv -t /somedirectory file_1 file_2

Unlike the cp command, you do not need a -r flag to move a directory. The bash mv command handles directories by default. While some users search for mv -r linux, this option is not necessary for moving directories with mv.
Important Options for the mv Command

By default, if you move a file to a destination where a file with the same name already exists, mv will overwrite it without warning. To prevent accidental data loss, you can use the following options:

    -i (interactive): This is a crucial safety feature. It will prompt you for confirmation before overwriting any existing file.

    mv -i source_file destination_directory

    -b (backup): If you intend to overwrite a file but want to keep the old version, this option creates a backup of the destination file. The backup is typically renamed with a tilde (~) suffix.

    mv -b file1 directory_with_file1

    -v (verbose): This option makes the mv command print out what it is doing, showing each file being moved or renamed.

    mv -v file1 file2 /somedirectory
- `zip <archive.zip> <files...>` — zip files
- `unzip <archive.zip>` — unzip files
- 'less' -
- 'more' - 
- 'history' - 
- 'history' - 
- The Exit Command

The most common way to end a shell session is with the exit command. When you type exit and press Enter, the current shell process terminates. This is a universal command that works in virtually any shell environment, making it a fundamental part of any beginner Linux tutorial.

exit

The Logout Command

Another command you can use for a terminal exit is logout. This command is specifically designed to terminate a login shell. While in many modern systems it behaves similarly to exit, it's good practice to know both commands.

logout

Closing the Terminal Window

If you are working within a graphical user interface (GUI), you also have the option to simply close the terminal window. This action typically sends a signal that terminates the shell session running inside it, providing a quick way to perform a terminal exit.

You've successfully learned how to navigate, work with files, and now, how to exit the shell. Take a well-deserved break, and we'll see you in the next course to continue your learning!
- alias

Typing long or repetitive commands can be tedious. Fortunately, you can create a shortcut, or a Linux alias, to make your command-line experience more efficient. The alias command lets you define a custom name for any command or sequence of commands.
Creating a Temporary Alias

To create a temporary alias that lasts for your current terminal session, you simply specify a name and set it equal to the command string.

For example, to create an alias named ll for the ls -la command, you would use the alias command linux syntax like this:

alias ll='ls -la'

Now, instead of typing ls -la, you can just type ll, and it will execute the same command. This is a simple yet powerful way to customize your shell.
Making an Alias Permanent

A temporary alias will disappear once you close your terminal or reboot your system. To make a command alias in linux permanent, you need to add it to your shell's configuration file. For the Bash shell, this file is typically ~/.bashrc.

    Open the file in a text editor: nano ~/.bashrc
    Add your alias definition to the file, just as you typed it on the command line:

alias ll='ls -la'
alias update='sudo apt update && sudo apt upgrade'

    Save the file and exit the editor.

For the changes to take effect, you must either close and reopen your terminal or tell the shell to reload the configuration file using the source command:

source ~/.bashrc

Your Linux command alias will now be available every time you start a new terminal session.
Removing an Alias

If you no longer need an alias, you can remove it with the unalias command. This will remove it from your current session.

unalias ll

To remove a permanent alias, you must also delete its definition from your ~/.bashrc file.

- help

When working on the Linux command line, you'll often need a quick reminder of how a command works or what options it accepts. Fortunately, Linux provides excellent tools for command line help right in the terminal.
The 'help' Command for Bash Built-ins

One of the most direct tools is help, a command that is built directly into the Bash shell. It is specifically designed to provide information about other Bash built-in commands. A built-in command is part of the shell itself, not a separate program. Examples include echo, cd, and pwd.

To use the Linux help command, simply type help followed by the name of the built-in command.

help echo

This will display a summary of the echo command, its syntax, and a list of available options. This is the fastest way to get assistance for shell-specific functions.
The --help Flag for Executable Programs

For most other executable programs that are not built into the shell, the help command won't work. Instead, a common convention is to provide a --help flag. This option signals the program to print a usage summary and then exit.

ls --help

While most developers adhere to this standard, it's not universal. However, trying the --help flag is usually the best first step to find help for an unfamiliar program. It's a fundamental skill for anyone learning about Linux commands.
- What is the whatis Command in Linux

The whatis command in Linux displays a concise, one-line description of a command directly from its manual (man) page. It's a quick way to get a reminder of a command's primary function without reading the entire man page. Think of the linux whatis command as a quick dictionary for your terminal.
How to Use the whatis Command

Using the whatis command linux is straightforward. Simply type whatis followed by the name of the command you want to know about. For example, if you're unsure about the cat command, you can run:

whatis cat

This will return a short description, such as "cat - concatenate files and print on the standard output".
Understanding the Output

The description provided by the linux whatis command is sourced directly from the NAME section of the command's manual page. This ensures the information is accurate and consistent with the system's documentation. If a command has multiple manual pages in different sections, whatis may display a line for each, helping you understand its various contexts.
- find

With countless files on a system, it can be challenging to locate a specific one. Fortunately, there's a powerful utility we can use for that: the find command. This tool is essential for efficient file management.
Using the Find Command Line

The basic syntax for the find command line is find [path] [expression]. You must specify the directory to search in and the criteria for what you're looking for.

For example, to search for a file named puppies.jpg within the /home directory and all its subdirectories, you would use:

find /home -name puppies.jpg

The find command in linux is highly flexible, allowing for many different search expressions.
Searching by Name and Type

One of the most common uses of the find command is searching by filename. As seen above, the -name option allows you to specify the exact name of the file you want to find.

You can also specify the type of item you are searching for. The -type option is used for this purpose. For instance, if you want to find a directory instead of a file, you can use d.

find /home -type d -name MyFolder

In this command, we set the type to d for directory and are searching for an item named MyFolder. To search specifically for regular files, you would use -type f.
Recursive Searching

A key feature of the find command linux users appreciate is its recursive nature. When you specify a starting directory, find doesn't just look in that single directory; it automatically searches through all subdirectories contained within it. This makes it an incredibly thorough tool for locating items anywhere in a directory tree.


## Info & Locators
- `which <command>` — find where command binaries live
- `whatis <command>` — one-line description of a command
- `man <command>` — displays the manual

## Permissions & Ownership
- `chmod <mode> <file>` — change file/directory permissions
- `chmod o+wx <file>` — add write and execute for **others**
- `chown <user>:<group> <file>` — change ownership

## Users & Groups
- `useradd <username>` — create a new user account
- `groupadd <groupname>` — create a new group
- `su - <user>` — switch to another user (root if omitted)
- `sudo <command>` — run a command with superuser (root) privileges

## Processes & Disk
- `kill <PID>` — terminate a running process by PID
- `df -h` — display disk space usage of filesystems (human readable)
- `head -n N <file>` — show first N lines (default 10)
- `tail -n N <file>` — show last N lines (default 10)

## Networking (basic)
- `ifconfig` — display or configure network interfaces (legacy)
- `ip addr` — show IP addresses and interfaces (modern replacement)
- `ping <host>` — test network connectivity
- `traceroute <host>` — show network path to destination

## Tools / Misc (from your list)
- `wget <url>` — download from internet (paste the URL)
- `git clone <repo>` — download a Git repository
- `apt` / `apt update` — package manager / update package list
- `fastfetch` — show system information (alternative to neofetch)
- `finger <user>` — show user account information
- `bc` — command-line calculator

## Network scanning / pentest tools (as you listed)
- `arpscan -l` — scan local network for active devices (arp-scan)
- `netdiscover` — detect live hosts on local network
- `nmap <target>` — network scanner to discover hosts/services
- `hydra` — brute-force testing tool (ethical use only)
- `dnsenum <domain>` — DNS enumeration for subdomains/records
