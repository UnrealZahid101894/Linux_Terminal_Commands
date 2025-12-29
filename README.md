# Linux Terminal Commands Reference

A comprehensive, well-organized guide to essential Linux terminal commands. Currently focused on **Zorin OS**, with plans to expand to other distributions.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Zorin OS](https://img.shields.io/badge/Zorin%20OS-Supported-brightgreen)
![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)

## 📋 Table of Contents

- [About This Repository](#about-this-repository)
- [⚡ Quick Reference - Most Used Commands](#-quick-reference---most-used-commands)
  - [Software Management](#software-management)
  - [System Control](#system-control)
  - [File Operations](#file-operations)
  - [Navigation](#navigation)
  - [Getting Help](#getting-help)
- [📚 Complete Command Reference](#-complete-command-reference)
  - [System Information](#system-information)
  - [Package Management](#package-management)
  - [File and Directory Operations](#file-and-directory-operations)
  - [File Search and Navigation](#file-search-and-navigation)
  - [File Permissions and Ownership](#file-permissions-and-ownership)
  - [Text Processing and Manipulation](#text-processing-and-manipulation)
  - [System Monitoring and Performance](#system-monitoring-and-performance)
  - [Process Management](#process-management)
  - [Network Operations](#network-operations)
  - [Disk and Storage Management](#disk-and-storage-management)
  - [User and Group Management](#user-and-group-management)
  - [System Services](#system-services)
  - [Compression and Archives](#compression-and-archives)
  - [System Maintenance](#system-maintenance)
  - [Shell Utilities](#shell-utilities)
- [Contributing](#contributing)
- [Roadmap](#roadmap)

---

## 🎯 About This Repository

This repository serves as a practical reference for Linux terminal commands, organized by category for easy navigation. Each command includes:
- **What it does**    : Clear explanation in simple terms
- **When to use it**  : Real-world scenarios
- **How to use it**   : Command syntax with common options
- **Examples**        : Copy-paste ready commands

**Current Support**   : Zorin OS (Ubuntu-based)  
**Coming Soon**       : Fedora, Arch Linux, openSUSE, and more

> 💡 **New to terminal?** Start with the [Quick Reference](#-quick-reference---most-used-commands) section below for the most commonly used commands!

---

## ⚡ Quick Reference - Most Used Commands

This section contains the commands you'll use 90% of the time. Bookmark this for quick access!

### Software Management

**Update your system (run this weekly)**
```bash
sudo apt update && sudo apt upgrade -y
```
💡 This checks for updates and installs them. Always do this before installing new software!

**Install a program**
```bash
sudo apt install program-name
```
📌 Example: `sudo apt install vlc` installs VLC media player

**Remove a program**
```bash
sudo apt remove program-name
```
📌 Example: `sudo apt remove vlc` removes VLC

**Completely remove a program (including settings)**
```bash
sudo apt purge program-name
```
💡 Use this when you want to start fresh with a program

**Search for a program**
```bash
apt search keyword
```
📌 Example: `apt search video editor` finds video editing software

**Clean up unused files**
```bash
sudo apt autoremove && sudo apt autoclean
```
💡 Run this monthly to free up disk space

---

### System Control

**Restart your computer**
```bash
sudo reboot
```

**Shut down your computer**
```bash
sudo shutdown now
```

**Shut down in 10 minutes**
```bash
sudo shutdown +10
```
💡 Cancel with: `sudo shutdown -c`

**Check how long system has been running**
```bash
uptime
```

---

### File Operations

**List files in current folder**
```bash
ls
```
💡 See more details: `ls -lah`

**Create a new folder**
```bash
mkdir folder-name
```
📌 Example: `mkdir Documents/Projects`

**Create multiple nested folders**
```bash
mkdir -p Documents/Work/2024/Reports
```

**Copy a file**
```bash
cp file.txt backup.txt
```

**Copy a folder**
```bash
cp -r folder/ backup-folder/
```

**Move or rename a file**
```bash
mv oldname.txt newname.txt
```
📌 Move example: `mv file.txt Documents/`

**Delete a file**
```bash
rm file.txt
```
⚠️ **Warning**: This is permanent! No recycle bin!

**Delete a folder**
```bash
rm -r folder-name/
```
⚠️ **Warning**: This deletes everything inside! Be careful!

**View a file's contents**
```bash
cat filename.txt
```
💡 For long files use: `less filename.txt` (press Q to quit)

**Edit a text file**
```bash
nano filename.txt
```
💡 Save: `Ctrl+O`, Exit: `Ctrl+X`

---

### Navigation

**Show current folder location**
```bash
pwd
```

**Go to your home folder**
```bash
cd ~
```
or just:
```bash
cd
```

**Go to a specific folder**
```bash
cd /path/to/folder
```
📌 Example: `cd Documents`

**Go up one folder level**
```bash
cd ..
```

**Go back to previous folder**
```bash
cd -
```

**Find a file by name**
```bash
find . -name "filename.txt"
```
📌 Example: `find ~ -name "*.pdf"` finds all PDFs in your home folder

**Quick search for files (faster)**
```bash
locate filename
```
💡 Update the database first: `sudo updatedb`

---

### Getting Help

**See what a command does**
```bash
man command-name
```
📌 Example: `man ls` shows the manual for ls command  
💡 Press Q to quit the manual

**Quick help for a command**
```bash
command-name --help
```
📌 Example: `cp --help`

**See previous commands you've typed**
```bash
history
```

**Search your command history**
```bash
history | grep keyword
```
📌 Example: `history | grep install`

**Repeat last command**
```bash
!!
```

**Clear the terminal screen**
```bash
clear
```
or press: `Ctrl+L`

---

## 📚 Complete Command Reference

Below is the comprehensive guide organized by category. Each section goes deeper into specific topics.

---

## 💻 System Information

Commands to check your system's hardware, software, and specifications.

### Get System Details

```bash
# Display system information
uname -a
```
**What it does**: Shows kernel name, version, and system architecture  
**When to use**: Checking your system type before installing software  
**Example Output**: `Linux zorin 5.15.0-76-generic x86_64`

```bash
# Show distribution information
lsb_release -a
```
**What it does**: Displays your Linux distribution details (name, version, codename)  
**When to use**: Finding your exact OS version for support or compatibility

```bash
# Display detailed hardware information
lscpu
```
**What it does**: Shows CPU architecture, cores, threads, and cache information  
**When to use**: Checking your processor specs before gaming or heavy tasks

```bash
# Show memory usage
free -h
```
**What it does**: Displays how much RAM and swap space you're using  
**When to use**: Checking if you need more RAM or why system is slow  
**Common options**: 
- `-h` = human-readable (shows GB/MB instead of bytes)
- `-m` = show in megabytes
- `-g` = show in gigabytes

```bash
# Display disk usage
df -h
```
**What it does**: Shows how much disk space is used and available on each drive  
**When to use**: Checking if you're running out of storage space  
**Common options**: 
- `-h` = human-readable sizes
- `-T` = show filesystem type

```bash
# Show detailed hardware information
lshw
```
**What it does**: Lists complete hardware configuration  
**When to use**: Getting detailed info about all your hardware  
**How to use**: `sudo lshw -short` (needs admin rights)

```bash
# Display PCI devices
lspci
```
**What it does**: Lists all PCI devices (graphics cards, network adapters, etc.)  
**When to use**: Checking what graphics card or network card you have

```bash
# Show USB devices
lsusb
```
**What it does**: Lists all USB devices connected to your system  
**When to use**: Checking if your USB device is detected

```bash
# Check system uptime
uptime
```
**What it does**: Shows how long system has been running and current load  
**When to use**: Checking if you need to restart after updates

---

## 📦 Package Management

Zorin OS uses **APT** (Advanced Package Tool) for installing and managing software.

> 💡 **Think of APT like an app store**: It downloads, installs, and updates all your programs from a central repository.

### Update and Upgrade System

```bash
# Update package lists
sudo apt update
```
**What it does**: Refreshes the list of available software and their versions  
**When to use**: ALWAYS run this first before installing anything or upgrading  
**Why**: Makes sure you get the latest version of software

```bash
# Upgrade installed packages
sudo apt upgrade
```
**What it does**: Updates all your installed programs to their newest versions  
**When to use**: Weekly, to keep your system secure and up-to-date  
**Important**: This won't remove any packages

```bash
# Full system upgrade
sudo apt full-upgrade
```
**What it does**: Like upgrade, but can also remove old packages if needed  
**When to use**: Monthly system maintenance or after major updates  
**Why different**: Handles complex dependency changes better

```bash
# One-liner: Update and upgrade together
sudo apt update && sudo apt upgrade -y
```
**What it does**: Updates the list then upgrades everything automatically  
**When to use**: Quick system update (the `-y` means "yes to all")

```bash
# Distribution upgrade
sudo apt dist-upgrade
```
**What it does**: Upgrades to a new OS version  
**When to use**: When Zorin releases a new major version  
**Warning**: Research first! This is a big change

---

### Install and Remove Software

```bash
# Install a package
sudo apt install package_name
```
**What it does**: Downloads and installs a program  
**Example**: `sudo apt install vlc` installs VLC media player  
**Example**: `sudo apt install gimp` installs GIMP image editor

```bash
# Install multiple packages at once
sudo apt install package1 package2 package3
```
**What it does**: Installs several programs in one command  
**Example**: `sudo apt install git curl wget` installs three tools at once  
**Why useful**: Saves time when setting up a new system

```bash
# Remove a package
sudo apt remove package_name
```
**What it does**: Uninstalls a program but keeps its settings  
**When to use**: When you might reinstall the program later  
**Example**: `sudo apt remove vlc`

```bash
# Completely remove a package
sudo apt purge package_name
```
**What it does**: Uninstalls a program AND deletes all its settings  
**When to use**: When you want a fresh start or freeing maximum space  
**Example**: `sudo apt purge firefox`

```bash
# Remove unused dependencies
sudo apt autoremove
```
**What it does**: Removes leftover packages that are no longer needed  
**When to use**: After removing software, to clean up  
**Why important**: Frees up disk space

```bash
# Complete cleanup command
sudo apt autoremove && sudo apt autoclean
```
**What it does**: Removes unused packages AND clears download cache  
**When to use**: Monthly maintenance to free disk space

---

### Search and Get Information

```bash
# Search for packages
apt search keyword
```
**What it does**: Finds programs matching your search  
**Example**: `apt search video editor` finds video editing software  
**Example**: `apt search screenshot` finds screenshot tools  
**Note**: You don't need `sudo` for searching

```bash
# Show package information
apt show package_name
```
**What it does**: Shows details about a program (description, version, size)  
**When to use**: Before installing, to see what the program does  
**Example**: `apt show gimp`

```bash
# List installed packages
apt list --installed
```
**What it does**: Shows every program you have installed  
**When to use**: Checking what's on your system  
**Tip**: Pipe to grep to search: `apt list --installed | grep vlc`

```bash
# List upgradable packages
apt list --upgradable
```
**What it does**: Shows which programs have updates available  
**When to use**: After `apt update`, to see what will be upgraded

```bash
# Check if a package is installed
dpkg -l | grep package_name
```
**What it does**: Searches your installed packages  
**Example**: `dpkg -l | grep firefox` checks if Firefox is installed

---

### Fix Problems

```bash
# Fix broken packages
sudo apt --fix-broken install
```
**What it does**: Repairs installation problems  
**When to use**: When installations fail or system says packages are broken  
**Also known as**: `sudo apt -f install`

```bash
# Reconfigure packages
sudo dpkg --configure -a
```
**What it does**: Completes incomplete package configurations  
**When to use**: When installations were interrupted

---

### Clean Up Disk Space

```bash
# Clean package cache
sudo apt clean
```
**What it does**: Deletes ALL downloaded package files  
**Space saved**: Can free several GB  
**Safe**: Yes, packages can be re-downloaded if needed

```bash
# Remove old package versions
sudo apt autoclean
```
**What it does**: Removes only outdated package files  
**When to use**: Prefer this over `clean` for regular maintenance  
**Why**: Keeps recent files in case you need to reinstall

---

## 📁 File and Directory Operations

### Navigation

```bash
# Print working directory
pwd
```
**Purpose**: Shows the current directory path

```bash
# Change directory
cd /path/to/directory
```
**Purpose**: Navigates to specified directory  
**Shortcuts**: `cd ~` (home), `cd ..` (parent), `cd -` (previous)

```bash
# List directory contents
ls
```
**Purpose**: Lists files and directories  
**Options**: `-l` (detailed), `-a` (show hidden), `-h` (human-readable sizes), `-t` (sort by time), `-R` (recursive)

**Common combinations**:
```bash
ls -lah    # Detailed list with hidden files and human-readable sizes
ls -lt     # Sort by modification time
ls -lS     # Sort by size
```

### Creating Files and Directories

```bash
# Create a new directory
mkdir directory_name
```
**Purpose**: Creates a new directory  
**Options**: `-p` (create parent directories)  
**Example**: `mkdir -p project/src/components`

```bash
# Create an empty file
touch filename.txt
```
**Purpose**: Creates a new empty file or updates timestamp of existing file

### Copying and Moving

```bash
# Copy files
cp source.txt destination.txt
```
**Purpose**: Copies a file  
**Options**: `-r` (recursive for directories), `-i` (interactive prompt), `-v` (verbose)

```bash
# Copy directory
cp -r source_dir/ destination_dir/
```
**Purpose**: Copies a directory and all its contents

```bash
# Move or rename
mv oldname.txt newname.txt
```
**Purpose**: Moves or renames files/directories  
**Example (move)**: `mv file.txt /home/user/Documents/`

### Deleting

```bash
# Remove file
rm filename.txt
```
**Purpose**: Deletes a file  
**Options**: `-i` (confirm before delete), `-f` (force), `-r` (recursive for directories)

```bash
# Remove empty directory
rmdir directory_name
```
**Purpose**: Removes an empty directory

```bash
# Remove directory with contents
rm -r directory_name
```
**Purpose**: Recursively removes directory and all contents  
**Warning**: Use with caution, especially with `-f` flag

### Viewing File Contents

```bash
# Display entire file
cat filename.txt
```
**Purpose**: Prints entire file content to terminal

```bash
# View file page by page
less filename.txt
```
**Purpose**: Opens file in a pager (navigate with arrows, q to quit)  
**Alternative**: `more filename.txt`

```bash
# Show first 10 lines
head filename.txt
```
**Purpose**: Displays first lines of a file  
**Options**: `-n 20` (show first 20 lines)

```bash
# Show last 10 lines
tail filename.txt
```
**Purpose**: Displays last lines of a file  
**Options**: `-f` (follow file updates in real-time), `-n 20` (last 20 lines)

```bash
# Count lines, words, characters
wc filename.txt
```
**Purpose**: Word count statistics  
**Options**: `-l` (lines only), `-w` (words only), `-c` (characters)

---

## 🔍 File Search and Navigation

### Find Files

```bash
# Find files by name
find /path -name "filename.txt"
```
**Purpose**: Searches for files matching exact name  
**Example**: `find /home -name "*.pdf"` (find all PDFs in home)

```bash
# Find files case-insensitive
find /path -iname "filename.txt"
```
**Purpose**: Searches for files ignoring case

```bash
# Find by type
find /path -type f    # files only
find /path -type d    # directories only
```
**Purpose**: Filters search by file type

```bash
# Find by size
find /path -size +100M
```
**Purpose**: Finds files larger than 100MB  
**Options**: `+` (greater), `-` (smaller), exact size without symbol

```bash
# Find and execute command
find /path -name "*.log" -exec rm {} \;
```
**Purpose**: Finds files and executes command on each  
**Example**: Delete all .log files

```bash
# Find recently modified files
find /path -mtime -7
```
**Purpose**: Finds files modified in last 7 days  
**Options**: `-mtime` (modified), `-atime` (accessed), `-ctime` (changed)

### Locate Files (Fast Search)

```bash
# Quick file search
locate filename
```
**Purpose**: Quickly finds files using pre-built database  
**Note**: Run `sudo updatedb` to update database first

```bash
# Case-insensitive locate
locate -i filename
```
**Purpose**: Searches ignoring case

### Which and Whereis

```bash
# Find command location
which command_name
```
**Purpose**: Shows the full path of shell commands  
**Example**: `which python3`

```bash
# Find binary, source, and manual
whereis command_name
```
**Purpose**: Locates binary, source code, and manual pages

---

## 🔐 File Permissions and Ownership

### Understanding Permissions

Permissions format: `rwxrwxrwx` (read, write, execute for owner, group, others)
- `r` (read) = 4
- `w` (write) = 2
- `x` (execute) = 1

### Changing Permissions

```bash
# Change permissions with numbers
chmod 755 filename.txt
```
**Purpose**: Sets permissions (owner: rwx, group: rx, others: rx)  
**Common values**: 
- `644` - Files (rw-r--r--)
- `755` - Executables and directories (rwxr-xr-x)
- `700` - Private files (rwx------)

```bash
# Change permissions with symbols
chmod u+x script.sh      # Add execute for user
chmod g-w file.txt       # Remove write for group
chmod o+r document.txt   # Add read for others
```
**Purpose**: Modifies specific permission bits  
**Symbols**: `u` (user), `g` (group), `o` (others), `a` (all)

```bash
# Recursive permission change
chmod -R 755 directory/
```
**Purpose**: Changes permissions for directory and all contents

### Changing Ownership

```bash
# Change file owner
sudo chown username filename.txt
```
**Purpose**: Changes file owner

```bash
# Change owner and group
sudo chown username:groupname filename.txt
```
**Purpose**: Changes both owner and group

```bash
# Recursive ownership change
sudo chown -R username:groupname directory/
```
**Purpose**: Changes ownership for directory and all contents

### View Permissions

```bash
# List with permissions
ls -l filename.txt
```
**Purpose**: Shows permissions, owner, group, size, and modification date

```bash
# Show file status
stat filename.txt
```
**Purpose**: Displays detailed file information including permissions in octal

---

## 📝 Text Processing and Manipulation

### Grep (Search Text)

```bash
# Search for pattern in file
grep "search_term" filename.txt
```
**Purpose**: Finds lines containing the search term  
**Options**: `-i` (ignore case), `-v` (invert match), `-n` (line numbers), `-r` (recursive)

```bash
# Search recursively in directory
grep -r "search_term" /path/to/directory
```
**Purpose**: Searches all files in directory and subdirectories

```bash
# Search with context
grep -C 3 "search_term" filename.txt
```
**Purpose**: Shows 3 lines before and after match  
**Options**: `-A 3` (after), `-B 3` (before)

```bash
# Count matches
grep -c "search_term" filename.txt
```
**Purpose**: Counts number of matching lines

### Sed (Stream Editor)

```bash
# Replace text in file
sed 's/old_text/new_text/' filename.txt
```
**Purpose**: Replaces first occurrence on each line

```bash
# Replace all occurrences
sed 's/old_text/new_text/g' filename.txt
```
**Purpose**: Replaces all occurrences globally

```bash
# Replace and save changes
sed -i 's/old_text/new_text/g' filename.txt
```
**Purpose**: Edits file in-place

```bash
# Delete lines containing pattern
sed '/pattern/d' filename.txt
```
**Purpose**: Removes lines matching pattern

### Awk (Text Processing)

```bash
# Print specific column
awk '{print $1}' filename.txt
```
**Purpose**: Prints first column of each line

```bash
# Print with condition
awk '$3 > 100 {print $1, $3}' data.txt
```
**Purpose**: Prints columns 1 and 3 where column 3 is greater than 100

```bash
# Use custom delimiter
awk -F: '{print $1}' /etc/passwd
```
**Purpose**: Prints first field using colon as separator

### Sort and Unique

```bash
# Sort lines
sort filename.txt
```
**Purpose**: Sorts lines alphabetically  
**Options**: `-r` (reverse), `-n` (numeric), `-k2` (sort by column 2)

```bash
# Remove duplicate lines
sort filename.txt | uniq
```
**Purpose**: Sorts and removes adjacent duplicates

```bash
# Count duplicate lines
sort filename.txt | uniq -c
```
**Purpose**: Counts occurrence of each unique line

### Cut (Extract Columns)

```bash
# Extract specific columns
cut -d: -f1,3 /etc/passwd
```
**Purpose**: Extracts fields 1 and 3 using colon as delimiter

```bash
# Extract characters
cut -c1-10 filename.txt
```
**Purpose**: Extracts characters 1 through 10 from each line

---

## 📊 System Monitoring and Performance

### Real-Time Monitoring

```bash
# Interactive process viewer
top
```
**Purpose**: Shows real-time system resource usage  
**Controls**: `q` (quit), `k` (kill process), `M` (sort by memory), `P` (sort by CPU)

```bash
# Enhanced process viewer
htop
```
**Purpose**: User-friendly alternative to top with colors and mouse support  
**Install**: `sudo apt install htop`

```bash
# Monitor system resources
vmstat 2
```
**Purpose**: Reports virtual memory statistics every 2 seconds

```bash
# I/O statistics
iostat
```
**Purpose**: Shows CPU and disk I/O statistics  
**Install**: `sudo apt install sysstat`

### Memory Usage

```bash
# Display memory usage
free -h
```
**Purpose**: Shows RAM and swap usage in human-readable format

```bash
# Show memory usage continuously
watch -n 2 free -h
```
**Purpose**: Updates memory display every 2 seconds

### Disk Usage

```bash
# Show directory sizes
du -h directory_name
```
**Purpose**: Displays disk usage of directory  
**Options**: `-s` (summary), `-a` (all files), `--max-depth=1` (limit depth)

```bash
# Show largest directories
du -h --max-depth=1 | sort -hr
```
**Purpose**: Lists directories sorted by size

```bash
# Disk usage with ncurses interface
ncdu /
```
**Purpose**: Interactive disk usage analyzer  
**Install**: `sudo apt install ncdu`

### System Logs

```bash
# View system log
journalctl
```
**Purpose**: Views systemd journal logs  
**Options**: `-f` (follow), `-u service_name` (specific service), `--since today`

```bash
# View kernel messages
dmesg
```
**Purpose**: Displays kernel ring buffer messages

```bash
# View authentication log
sudo tail -f /var/log/auth.log
```
**Purpose**: Monitors authentication attempts in real-time

---

## ⚙️ Process Management

### List Processes

```bash
# List all processes
ps aux
```
**Purpose**: Shows all running processes with detailed information  
**Columns**: USER, PID, CPU%, MEM%, COMMAND

```bash
# List processes in tree format
pstree
```
**Purpose**: Displays processes in hierarchical tree structure

```bash
# Find specific process
ps aux | grep process_name
```
**Purpose**: Searches for specific process

```bash
# Show processes for current user
ps ux
```
**Purpose**: Lists processes owned by current user

### Kill Processes

```bash
# Terminate process by PID
kill PID
```
**Purpose**: Sends TERM signal to process (graceful shutdown)

```bash
# Force kill process
kill -9 PID
```
**Purpose**: Sends KILL signal (immediate termination)

```bash
# Kill process by name
killall process_name
```
**Purpose**: Terminates all processes with matching name

```bash
# Interactive kill
pkill -i process_name
```
**Purpose**: Kills processes matching pattern (case-insensitive with `-i`)

### Background and Foreground

```bash
# Run command in background
command &
```
**Purpose**: Starts command in background

```bash
# List background jobs
jobs
```
**Purpose**: Shows current background jobs

```bash
# Bring job to foreground
fg %1
```
**Purpose**: Brings job number 1 to foreground

```bash
# Send current process to background
Ctrl+Z    # Suspend
bg        # Continue in background
```
**Purpose**: Suspends current process and continues it in background

### Process Priority

```bash
# Start with priority
nice -n 10 command
```
**Purpose**: Starts command with specified priority (-20 to 19, higher = lower priority)

```bash
# Change priority of running process
renice -n 5 -p PID
```
**Purpose**: Changes priority of running process

---

## 🌐 Network Operations

### Network Configuration

```bash
# Show IP addresses
ip addr show
```
**Purpose**: Displays all network interfaces and IP addresses  
**Alternative**: `ip a`

```bash
# Show routing table
ip route show
```
**Purpose**: Displays routing table

```bash
# Legacy network info
ifconfig
```
**Purpose**: Shows network interface configuration  
**Install**: `sudo apt install net-tools`

### Network Connectivity

```bash
# Test connectivity
ping google.com
```
**Purpose**: Sends ICMP packets to test network connectivity  
**Options**: `-c 4` (send 4 packets then stop)

```bash
# Trace route to host
traceroute google.com
```
**Purpose**: Shows path packets take to destination  
**Install**: `sudo apt install traceroute`

```bash
# DNS lookup
nslookup google.com
```
**Purpose**: Queries DNS for domain information

```bash
# Detailed DNS lookup
dig google.com
```
**Purpose**: Performs detailed DNS queries  
**Install**: `sudo apt install dnsutils`

### Network Monitoring

```bash
# Show network connections
netstat -tuln
```
**Purpose**: Lists all listening ports and established connections  
**Options**: `-t` (TCP), `-u` (UDP), `-l` (listening), `-n` (numeric)

```bash
# Modern alternative to netstat
ss -tuln
```
**Purpose**: Faster and more detailed socket statistics

```bash
# Monitor bandwidth
iftop
```
**Purpose**: Shows bandwidth usage by connection  
**Install**: `sudo apt install iftop`, **Usage**: `sudo iftop`

```bash
# Network bandwidth monitor
nload
```
**Purpose**: Displays incoming and outgoing traffic  
**Install**: `sudo apt install nload`

### Download Files

```bash
# Download file
wget https://example.com/file.zip
```
**Purpose**: Downloads files from the internet  
**Options**: `-c` (continue), `-O` (output filename)

```bash
# Alternative download tool
curl -O https://example.com/file.zip
```
**Purpose**: Transfers data from URLs  
**Options**: `-L` (follow redirects), `-o filename` (save as)

### Firewall

```bash
# Show firewall status
sudo ufw status
```
**Purpose**: Displays UFW (Uncomplicated Firewall) status

```bash
# Enable firewall
sudo ufw enable
```
**Purpose**: Activates firewall

```bash
# Allow port
sudo ufw allow 80/tcp
```
**Purpose**: Opens specific port

```bash
# Deny port
sudo ufw deny 23/tcp
```
**Purpose**: Blocks specific port

---

## 💾 Disk and Storage Management

### Disk Information

```bash
# List block devices
lsblk
```
**Purpose**: Shows all storage devices and partitions in tree format

```bash
# Show disk usage by filesystem
df -h
```
**Purpose**: Displays disk space usage for all mounted filesystems

```bash
# Detailed disk info
sudo fdisk -l
```
**Purpose**: Lists all disks and partitions with detailed information

### Mounting and Unmounting

```bash
# Mount a device
sudo mount /dev/sdb1 /mnt/usb
```
**Purpose**: Mounts a partition to specified directory

```bash
# Unmount device
sudo umount /mnt/usb
```
**Purpose**: Unmounts a mounted filesystem

```bash
# Show mounted filesystems
mount | grep ^/dev
```
**Purpose**: Lists currently mounted devices

### Partition Management

```bash
# Interactive partition editor
sudo fdisk /dev/sdb
```
**Purpose**: Manages disk partitions (create, delete, modify)

```bash
# GUI partition manager
sudo gparted
```
**Purpose**: Graphical partition editor  
**Install**: `sudo apt install gparted`

### Check Disk Health

```bash
# Check filesystem
sudo fsck /dev/sdb1
```
**Purpose**: Checks and repairs filesystem  
**Warning**: Only run on unmounted filesystems

```bash
# SMART disk health
sudo smartctl -a /dev/sda
```
**Purpose**: Shows disk health status  
**Install**: `sudo apt install smartmontools`

---

## 👥 User and Group Management

### User Operations

```bash
# Add new user
sudo adduser username
```
**Purpose**: Creates new user with home directory

```bash
# Delete user
sudo deluser username
```
**Purpose**: Removes user account  
**Options**: `--remove-home` (also delete home directory)

```bash
# Change password
passwd
```
**Purpose**: Changes password for current user  
**For other users**: `sudo passwd username`

```bash
# Switch user
su - username
```
**Purpose**: Switches to another user account

```bash
# Execute command as another user
sudo -u username command
```
**Purpose**: Runs command as specified user

### Group Operations

```bash
# Add new group
sudo groupadd groupname
```
**Purpose**: Creates new group

```bash
# Add user to group
sudo usermod -aG groupname username
```
**Purpose**: Adds user to supplementary group  
**Note**: `-a` appends to existing groups, `-G` specifies groups

```bash
# Remove user from group
sudo deluser username groupname
```
**Purpose**: Removes user from specified group

```bash
# List user's groups
groups username
```
**Purpose**: Shows all groups user belongs to

### User Information

```bash
# Show current user
whoami
```
**Purpose**: Displays current username

```bash
# Show logged-in users
who
```
**Purpose**: Lists all currently logged-in users

```bash
# Detailed user info
id username
```
**Purpose**: Shows user ID, group ID, and groups

---

## 🔧 System Services

Zorin OS uses **systemd** for service management.

### Service Control

```bash
# Start a service
sudo systemctl start service_name
```
**Purpose**: Starts a service  
**Example**: `sudo systemctl start apache2`

```bash
# Stop a service
sudo systemctl stop service_name
```
**Purpose**: Stops a running service

```bash
# Restart a service
sudo systemctl restart service_name
```
**Purpose**: Stops and then starts a service

```bash
# Reload service configuration
sudo systemctl reload service_name
```
**Purpose**: Reloads configuration without stopping service

### Service Status

```bash
# Check service status
sudo systemctl status service_name
```
**Purpose**: Shows detailed status of a service

```bash
# Check if service is active
systemctl is-active service_name
```
**Purpose**: Returns active/inactive status

```bash
# Check if service is enabled
systemctl is-enabled service_name
```
**Purpose**: Returns enabled/disabled status

### Enable/Disable Services

```bash
# Enable service at boot
sudo systemctl enable service_name
```
**Purpose**: Configures service to start automatically at boot

```bash
# Disable service at boot
sudo systemctl disable service_name
```
**Purpose**: Prevents service from starting at boot

```bash
# Enable and start service
sudo systemctl enable --now service_name
```
**Purpose**: Enables service and starts it immediately

### List Services

```bash
# List all services
systemctl list-units --type=service
```
**Purpose**: Shows all loaded services

```bash
# List running services
systemctl list-units --type=service --state=running
```
**Purpose**: Shows only running services

```bash
# List failed services
systemctl --failed
```
**Purpose**: Shows services that failed to start

---

## 🗜️ Compression and Archives

### Tar Archives

```bash
# Create tar archive
tar -cvf archive.tar directory/
```
**Purpose**: Creates uncompressed tar archive  
**Options**: `-c` (create), `-v` (verbose), `-f` (filename)

```bash
# Create tar.gz (compressed)
tar -czvf archive.tar.gz directory/
```
**Purpose**: Creates gzip-compressed tar archive  
**Option**: `-z` (gzip compression)

```bash
# Create tar.bz2 (better compression)
tar -cjvf archive.tar.bz2 directory/
```
**Purpose**: Creates bzip2-compressed tar archive  
**Option**: `-j` (bzip2 compression)

```bash
# Extract tar archive
tar -xvf archive.tar
```
**Purpose**: Extracts tar archive  
**Option**: `-x` (extract)

```bash
# Extract tar.gz
tar -xzvf archive.tar.gz
```
**Purpose**: Extracts gzip-compressed archive

```bash
# List archive contents
tar -tvf archive.tar
```
**Purpose**: Lists files in archive without extracting  
**Option**: `-t` (list)

```bash
# Extract to specific directory
tar -xzvf archive.tar.gz -C /path/to/directory
```
**Purpose**: Extracts to specified location

### Zip Archives

```bash
# Create zip archive
zip -r archive.zip directory/
```
**Purpose**: Creates zip archive  
**Option**: `-r` (recursive)

```bash
# Extract zip archive
unzip archive.zip
```
**Purpose**: Extracts zip archive

```bash
# List zip contents
unzip -l archive.zip
```
**Purpose**: Lists files without extracting

```bash
# Extract to specific directory
unzip archive.zip -d /path/to/directory
```
**Purpose**: Extracts to specified location

### Gzip (Individual Files)

```bash
# Compress file
gzip filename.txt
```
**Purpose**: Compresses file (creates filename.txt.gz, removes original)

```bash
# Decompress file
gunzip filename.txt.gz
```
**Purpose**: Decompresses file

```bash
# Keep original file
gzip -k filename.txt
```
**Purpose**: Compresses while keeping original

---

## 🛠️ System Maintenance

### System Updates

```bash
# Full system update routine
sudo apt update && sudo apt upgrade -y && sudo apt autoremove -y
```
**Purpose**: Updates, upgrades, and cleans up in one command

### Disk Cleanup

```bash
# Clean package cache
sudo apt clean && sudo apt autoclean
```
**Purpose**: Removes old package files

```bash
# Remove old kernels
sudo apt autoremove --purge
```
**Purpose**: Removes unused kernels and packages

```bash
# Clean thumbnail cache
rm -rf ~/.cache/thumbnails/*
```
**Purpose**: Clears thumbnail cache

```bash
# Clean journal logs
sudo journalctl --vacuum-time=7d
```
**Purpose**: Keeps only last 7 days of logs

### Check System Issues

```bash
# Verify package integrity
sudo apt check
```
**Purpose**: Checks for broken dependencies

```bash
# Fix broken packages
sudo apt --fix-broken install
```
**Purpose**: Attempts to fix broken package dependencies

```bash
# Configure pending packages
sudo dpkg --configure -a
```
**Purpose**: Configures unpacked but not configured packages

### Scheduled Tasks

```bash
# Edit user cron jobs
crontab -e
```
**Purpose**: Opens crontab editor for scheduled tasks

```bash
# List cron jobs
crontab -l
```
**Purpose**: Lists scheduled cron jobs

```bash
# System-wide cron
sudo nano /etc/crontab
```
**Purpose**: Edits system-wide cron jobs

---

## 🐚 Shell Utilities

### Command History

```bash
# Show command history
history
```
**Purpose**: Lists previously executed commands

```bash
# Search history
history | grep search_term
```
**Purpose**: Searches command history

```bash
# Execute command from history
!123
```
**Purpose**: Re-runs command number 123 from history

```bash
# Execute last command
!!
```
**Purpose**: Repeats last command

```bash
# Clear history
history -c
```
**Purpose**: Clears command history

### Aliases

```bash
# Create alias
alias ll='ls -lah'
```
**Purpose**: Creates command shortcut

```bash
# List aliases
alias
```
**Purpose**: Shows all defined aliases

```bash
# Make alias permanent
echo "alias ll='ls -lah'" >> ~/.bashrc
source ~/.bashrc
```
**Purpose**: Adds alias to bashrc and reloads

### Environment Variables

```bash
# Show all variables
env
```
**Purpose**: Lists all environment variables

```bash
# Show specific variable
echo $PATH
```
**Purpose**: Displays value of PATH variable

```bash
# Set temporary variable
export VARIABLE_NAME="value"
```
**Purpose**: Sets variable for current session

```bash
# Set permanent variable
echo 'export VARIABLE_NAME="value"' >> ~/.bashrc
source ~/.bashrc
```
**Purpose**: Adds variable to bashrc

### Redirection and Pipes

```bash
# Redirect output to file
command > output.txt
```
**Purpose**: Writes command output to file (overwrites)

```bash
# Append to file
command >> output.txt
```
**Purpose**: Appends command output to file

```bash
# Redirect errors
command 2> errors.txt
```
**Purpose**: Redirects error messages to file

```bash
# Redirect both output and errors
command &> all_output.txt
```
**Purpose**: Redirects stdout and stderr to file

```bash
# Pipe commands
