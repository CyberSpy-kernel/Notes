# Linux

## Overview
This is the sample text for overview.

## Fiel System

- / - root directory
    - /root - The super-user's home directory
    - /boot - The kernel images is in here
    - /etc - System configuration files
    - /home - User's directories are under here
    - /mnt - General purpose mount point
    - /proc - A view of internal kernel data
    - /sys - The kernel's view of the hardware
    - /dev - Special device files live here
    - /bin - Executables
    - /sbin - Executables
    - /lib - Libraries
    - /usr
        - bin - more executables 
        - lib - More libraries

## `ls` Commands

### Basic Commands
- `ls`: List files and directories in the current directory.
- `ls [directory]`: List files and directories in the specified directory.

### Options
- `ls -a`: List all files, including hidden files.
- `ls -A`: List all files except `.` (current directory) and `..` (parent directory).
- `ls -l`: List files in long format, showing detailed information.
- `ls -h`: With `-l`, print sizes in human-readable format (e.g., 1K 234M 2G).
- `ls -r`: Reverse the order while sorting.
- `ls -R`: Recursively list subdirectories.
- `ls -d`: List directories themselves, not their contents.
- `ls -t`: Sort by modification time, newest first.
- `ls -S`: Sort by file size, largest first.
- `ls -X`: Sort by extension.
- `ls -1`: List one file per line.
- `ls -Q`: Enclose entry names in double quotes.
- `ls -i`: Print the index number (inode) of each file.
- `ls -n`: With `-l`, list numeric UID and GID.
- `ls -o`: With `-l`, list without group information.
- `ls -c`: With `-l`, sort by and show ctime (time of last modification of file status information).
- `ls -u`: With `-l`, sort by and show access time.
- `ls --color`: Colorize the output.
- `ls --full-time`: With `-l`, list full date and time.
- `ls --group-directories-first`: Group directories before files.
- `ls --time-style`: With `-l`, show times using specified style (e.g., `full-iso`, `long-iso`, etc.).

### Combining Options
- `ls -al`: List all files in long format.
- `ls -lh`: List files in long format with human-readable file sizes.
- `ls -lt`: List files sorted by modification time in long format.
- `ls -lrt`: List files sorted by modification time in reverse order in long format.
- `ls -lS`: List files sorted by size in long format.
- `ls -lhS`: List files sorted by size in long format with human-readable file sizes.
- `ls -laR`: List all files, including hidden ones, recursively.

### Examples
- `ls`: Basic listing of current directory.
- `ls -a`: List all files, including hidden ones, in the current directory.
- `ls -lh`: Long listing with human-readable file sizes.
- `ls -lt`: Long listing sorted by modification time.
- `ls -laR`: Recursively list all files, including hidden ones, in all subdirectories.
- `ls -d */`: List only directories in the current directory.
- `ls --color`: List files with color-coded output based on file type.

By using these `ls` commands, you can effectively navigate and manage directories and files in Unix-like operating systems. Experiment with different combinations of options to find the output format that best suits your needs.

## Linux Commands
```
# Get user-name
$ whoami

# You will get 'root' as output after executing below
$ sudo whoami

# change directory
$ cd

# list files and folders
$ ls
$ ls -a
$ ls -l
$ ls -la

# Current working directory
$ pwd


```
