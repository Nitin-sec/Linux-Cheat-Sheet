# Linux Commands — (My notes)

## File & Directory
- `pwd` — to see where we are
- `ls` — to see surrounding
- `cd <path>` / `cd ..` — change directory / go back
- `mkdir <dir>` — make directories
- `rmdir <dir>` — remove directories
- `touch <file>` — create an empty file

## Edit / View Files
- `mousepad <file>` — GUI editor to write or change files
- `nano <file>` — terminal editor to create/edit files
- `cat <file>` — view, create, concatenate, copy text files
- `truncate -s 0 <file>` — remove file content (empty file)
- `echo "text"` — print text to terminal or redirect into files

## File Ops
- `rm <file>` — delete a file
- `cp <src> <dst>` — copy file or directory
- `mv <src> <dst>` — move / rename (cut & paste)
- `zip <archive.zip> <files...>` — zip files
- `unzip <archive.zip>` — unzip files

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
