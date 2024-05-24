# Common Linux Commands

This document provides a list of common Linux commands along with brief descriptions.

## File and Directory Management

| Command | Description                           |
|---------|---------------------------------------|
| `ls`    | List directory contents.              |
| `cd`    | Change the current directory.         |
| `pwd`   | Print the current working directory.  |
| `mkdir` | Create new directories.               |
| `rmdir` | Remove empty directories.             |
| `rm`    | Remove files or directories.          |
| `cp`    | Copy files or directories.            |
| `mv`    | Move or rename files or directories.  |
| `touch` | Create empty files or update file timestamps. |
| `cat`   | Concatenate and display file contents.|
| `more`  | View file contents one screen at a time. |
| `less`  | View file contents with backward movement. |
| `head`  | Display the first lines of a file.    |
| `tail`  | Display the last lines of a file.     |
| `find`  | Search for files in a directory hierarchy. |
| `locate`| Find files by name.                   |
| `./`    |	Runs an executable.                   |

## File Permissions and Ownership

| Command | Description                           |
|---------|---------------------------------------|
| `chmod` | Change file modes or Access Control Lists. |
| `chown` | Change file owner and group.          |
| `chgrp` | Change group ownership.               |

## System Information and Management

| Command   | Description                                     |
|-----------|-------------------------------------------------|
| `uname`   | Print system information.                       |
| `top`     | Display Linux tasks.                            |
| `ps`      | Report a snapshot of current processes.         |
| `df`      | Report file system disk space usage.            |
| `du`      | Estimate file space usage.                      |
| `free`    | Display amount of free and used memory in the system. |
| `uptime`  | Tell how long the system has been running.      |
| `who`     | Show who is logged on.                          |
| `whoami`  | Print the current user name.                    |
| `hostname`| Show or set the system’s hostname.              |
| `kill`    |	Terminates programs.                            |
| `htop`    |	Displays processes and resources information.   |

## Networking

| Command  | Description                                       |
|----------|---------------------------------------------------|
| `ping`   | Send ICMP ECHO_REQUEST to network hosts.          |
| `ifconfig`| Configure a network interface (deprecated, use `ip`). |
| `ip`     | Show/manipulate routing, devices, policy routing, and tunnels. |
| `netstat`| Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships. |
| `scp`    | Secure copy (remote file copy program).           |
| `ssh`    | OpenSSH SSH client (remote login program).        |
| `wget`   | The non-interactive network downloader.           |
| `curl`   | Transfer data from or to a server.                |

## Text Processing

| Command | Description                                       |
|---------|---------------------------------------------------|
| `grep`  | Print lines that match patterns.                  |
| `awk`   | Pattern scanning and processing language.         |
| `sed`   | Stream editor for filtering and transforming text.|
| `cut`   | Remove sections from each line of files.          |
| `sort`  | Sort lines of text files.                         |
| `uniq`  | Report or omit repeated lines.                    |
| `wc`    | Print newline, word, and byte counts for each file.|
| `shred` |	Overwrites a file to hide its contents            |

## Compression and Archiving

| Command | Description                                       |
|---------|---------------------------------------------------|
| `tar`   | Archive files.                                    |
| `gzip`  | Compress files.                                   |
| `gunzip`| Decompress files.                                 |
| `zip`   | Package and compress (archive) files.             |
| `unzip` | List, test and extract compressed files in a ZIP archive. |

## Package Management (varies by distribution)

| Command  | Description                                      |
|----------|--------------------------------------------------|
| `apt-get`| APT package handling utility (Debian/Ubuntu).    |
| `yum`    | Package manager for RPM-based distributions (CentOS/RHEL). |
| `dnf`    | Next generation package manager for RPM-based distributions (Fedora). |
| `zypper` | Command line interface of ZYpp package manager (openSUSE). |

## Disk Management

| Command | Description                                      |
|---------|--------------------------------------------------|
| `fdisk` | Partition table manipulator for Linux.           |
| `mkfs`  | Build a Linux file system.                       |
| `mount` | Mount a file system.                             |
| `umount`| Unmount file systems.                            |

## User Management

| Command  | Description                                      |
|----------|--------------------------------------------------|
| `adduser`| Add a user to the system.                        |
| `useradd`| Create a new user or update default new user information. |
| `passwd` | Update user's authentication tokens.             |
| `usermod`| Modify a user account.                           |
| `deluser`| Remove a user from the system.                   |
| `userdel`| Delete a user account and related files.         |

## Miscellaneous

| Command  | Description                                      |
|----------|--------------------------------------------------|
| `man`    |	Displays manual page of other commands          |
| `which`  |	Returns the full binary path of a program       |
| `echo`   | Display a line of text.                          |
| `date`   | Display or set the system date and time.         |
| `cal`    | Display a calendar.                              |
| `alias`  | Define or display aliases.                       |
| `history`| Display or manipulate the history list.          |
| `shutdown`| Bring the system down.                          |


