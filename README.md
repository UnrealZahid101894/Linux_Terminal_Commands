# Linux Terminal Commands Reference

A comprehensive, well-organized guide to essential Linux terminal commands. Currently focused on **Zorin OS**, with plans to expand to other distributions.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Zorin OS](https://img.shields.io/badge/Zorin%20OS-Supported-brightgreen)
![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)

## 📋 Table of Contents

- [About This Repository](#about-this-repository)
- [⚡ Quick Reference - Most Used Commands](#-quick-reference---most-used-commands)
- [📚 Complete Command Reference](#-complete-command-reference)
- [Contributing](#contributing)
- [Roadmap](#roadmap)

---

## 🎯 About This Repository

This repository serves as a practical reference for Linux terminal commands, organized by category for easy navigation. Each command includes:
- **What it does**: Clear explanation in simple terms
- **When to use it**: Real-world scenarios
- **How to use it**: Command syntax with common options
- **Examples**: Copy-paste ready commands

**Current Support**: Zorin OS (Ubuntu-based)  
**Coming Soon**: Fedora, Arch Linux, openSUSE, and more

> 💡 **New to terminal?** Start with the [Quick Reference](#-quick-reference---most-used-commands) section below for the most commonly used commands!

---

## ⚡ Quick Reference - Most Used Commands

This section contains the commands you'll use 90% of the time. Bookmark this for quick access!

### Software Management

| Command | What It Does | Example |
|---------|-------------|---------|
| `sudo apt update && sudo apt upgrade -y` | Updates package lists and installs all available updates | Run weekly to keep system secure |
| `sudo apt install <package>` | Installs a program | `sudo apt install vlc` |
| `sudo apt remove <package>` | Removes a program (keeps settings) | `sudo apt remove vlc` |
| `sudo apt purge <package>` | Completely removes a program including settings | `sudo apt purge firefox` |
| `apt search <keyword>` | Searches for available programs | `apt search video editor` |
| `sudo apt autoremove && sudo apt autoclean` | Cleans up unused files and packages | Run monthly to free disk space |

💡 **Pro Tip**: Always run `sudo apt update` before installing new software to get the latest versions!

---

### System Control

| Command | What It Does | Notes |
|---------|-------------|-------|
| `sudo reboot` | Restarts your computer | Immediately reboots |
| `sudo shutdown now` | Shuts down immediately | Powers off the system |
| `sudo shutdown +10` | Schedules shutdown in 10 minutes | Cancel with `sudo shutdown -c` |
| `uptime` | Shows how long system has been running | Also displays system load |

---

### File Operations

| Command | What It Does | Example |
|---------|-------------|---------|
| `ls` | Lists files in current folder | Use `ls -lah` for detailed view |
| `mkdir <name>` | Creates a new folder | `mkdir Documents/Projects` |
| `mkdir -p <path>` | Creates nested folders | `mkdir -p Work/2024/Reports` |
| `cp <source> <dest>` | Copies a file | `cp file.txt backup.txt` |
| `cp -r <source> <dest>` | Copies a folder and contents | `cp -r folder/ backup/` |
| `mv <old> <new>` | Moves or renames a file | `mv file.txt Documents/` |
| `rm <file>` | Deletes a file (⚠️ permanent!) | No recycle bin - be careful! |
| `rm -r <folder>` | Deletes a folder (⚠️ permanent!) | Deletes everything inside |
| `cat <file>` | Views file contents | For long files use `less` |
| `nano <file>` | Edits a text file | Save: Ctrl+O, Exit: Ctrl+X |

⚠️ **Warning**: `rm` commands are permanent - there's no recycle bin in terminal!

---

### Navigation

| Command | What It Does | Example |
|---------|-------------|---------|
| `pwd` | Shows current folder location | Prints full path |
| `cd ~` or `cd` | Goes to your home folder | Quick way home |
| `cd <path>` | Changes to specified folder | `cd Documents` |
| `cd ..` | Goes up one folder level | Navigate to parent directory |
| `cd -` | Returns to previous folder | Toggle between two locations |
| `find . -name "<pattern>"` | Finds files by name | `find ~ -name "*.pdf"` |
| `locate <filename>` | Quick file search (faster) | Run `sudo updatedb` first |

---

### Getting Help

| Command | What It Does | Example |
|---------|-------------|---------|
| `man <command>` | Shows detailed manual for a command | `man ls` (press Q to quit) |
| `<command> --help` | Shows quick help summary | `cp --help` |
| `history` | Shows previously typed commands | View your command history |
| `history \| grep <keyword>` | Searches command history | `history \| grep install` |
| `!!` | Repeats last command | Quick way to re-run |
| `clear` or `Ctrl+L` | Clears the terminal screen | Cleans up your view |

---

## 📚 Complete Command Reference

Below is the comprehensive guide organized by category. Each section goes deeper into specific topics.

---

## 💻 System Information

### Basic System Info

| Command | What It Does | When to Use | Common Options |
|---------|-------------|-------------|----------------|
| `uname -a` | Shows kernel and system architecture | Checking system type before installing software | `-r` (kernel only), `-m` (machine type) |
| `lsb_release -a` | Displays Linux distribution details | Finding exact OS version for support | `-d` (description only) |
| `hostnamectl` | Shows system hostname and OS info | Quick system overview | N/A |

### Hardware Information

| Command | What It Does | When to Use | Common Options |
|---------|-------------|-------------|----------------|
| `lscpu` | Shows CPU details (cores, threads, cache) | Checking processor specs | `-e` (extended format) |
| `lshw` | Lists complete hardware configuration | Getting detailed hardware info | `-short` (brief), `-html` (web format) |
| `lspci` | Lists PCI devices (GPU, network cards) | Checking graphics/network hardware | `-v` (verbose) |
| `lsusb` | Shows connected USB devices | Verifying USB device detection | `-v` (verbose) |
| `lsblk` | Lists all storage devices | Viewing disk structure | `-f` (filesystems) |

### Memory and Storage

| Command | What It Does | When to Use | Common Options |
|---------|-------------|-------------|----------------|
| `free -h` | Shows RAM and swap usage | Checking available memory | `-m` (MB), `-g` (GB) |
| `df -h` | Displays disk space usage | Checking storage availability | `-T` (show filesystem type) |
| `uptime` | Shows system uptime and load | Checking system stability | N/A |

---

## 📦 Package Management

### Update and Upgrade

| Command | What It Does | When to Use | Notes |
|---------|-------------|-------------|-------|
| `sudo apt update` | Refreshes package lists | Before installing/upgrading anything | Doesn't install updates |
| `sudo apt upgrade` | Upgrades all installed packages | Weekly system maintenance | Won't remove packages |
| `sudo apt full-upgrade` | Full system upgrade (can remove packages) | Monthly or after major updates | Handles dependencies better |
| `sudo apt dist-upgrade` | Upgrades to new OS version | Major version releases | Research first! |

### Install and Remove

| Command | What It Does | When to Use | Examples |
|---------|-------------|-------------|----------|
| `sudo apt install <package>` | Installs a program | Installing new software | `sudo apt install vlc gimp` |
| `sudo apt remove <package>` | Uninstalls program (keeps settings) | Temporary removal | `sudo apt remove firefox` |
| `sudo apt purge <package>` | Completely removes program + settings | Clean removal | `sudo apt purge firefox` |
| `sudo apt autoremove` | Removes unused dependencies | After removing software | Frees disk space |

### Search and Information

| Command | What It Does | When to Use | Notes |
|---------|-------------|-------------|-------|
| `apt search <keyword>` | Searches for packages | Finding software | No sudo needed |
| `apt show <package>` | Shows package details | Before installing | Displays description, size, version |
| `apt list --installed` | Lists all installed packages | System audit | Pipe to grep for searching |
| `apt list --upgradable` | Shows available updates | After `apt update` | See what will upgrade |

### Fix Problems

| Command | What It Does | When to Use |
|---------|-------------|-------------|
| `sudo apt --fix-broken install` | Repairs broken packages | Installation failures |
| `sudo dpkg --configure -a` | Completes interrupted installations | After interrupted installs |
| `sudo apt clean` | Clears all cached packages | Free several GB |
| `sudo apt autoclean` | Removes old cached packages only | Regular maintenance |

---

## 📁 File and Directory Operations

### Navigation

| Command | What It Does | Shortcuts & Tips |
|---------|-------------|------------------|
| `pwd` | Prints current directory path | Shows where you are |
| `cd <path>` | Changes directory | `cd ~` (home), `cd ..` (up), `cd -` (previous) |
| `ls` | Lists directory contents | `-l` (detailed), `-a` (hidden), `-h` (sizes) |
| `ls -lah` | Detailed list with hidden files | Most useful ls combination |
| `ls -lt` | Lists sorted by modification time | Find recent files |
| `ls -lS` | Lists sorted by size | Find large files |

### Creating and Copying

| Command | What It Does | Examples | Options |
|---------|-------------|----------|---------|
| `mkdir <name>` | Creates directory | `mkdir Projects` | `-p` (create parents) |
| `mkdir -p <path>` | Creates nested directories | `mkdir -p a/b/c` | Creates all at once |
| `touch <file>` | Creates empty file | `touch notes.txt` | Updates timestamp if exists |
| `cp <src> <dst>` | Copies file | `cp file.txt backup.txt` | `-i` (confirm), `-v` (verbose) |
| `cp -r <src> <dst>` | Copies directory recursively | `cp -r dir/ backup/` | Required for directories |

### Moving and Deleting

| Command | What It Does | Examples | ⚠️ Warnings |
|---------|-------------|----------|-----------|
| `mv <old> <new>` | Moves or renames | `mv file.txt docs/` | Can overwrite! |
| `rm <file>` | Removes file | `rm test.txt` | Permanent deletion! |
| `rm -r <dir>` | Removes directory | `rm -r folder/` | Deletes all contents! |
| `rm -rf <dir>` | Force remove directory | Use with caution | No confirmation! |
| `rmdir <dir>` | Removes empty directory | `rmdir temp/` | Only works if empty |

### Viewing Files

| Command | What It Does | When to Use | Controls |
|---------|-------------|-------------|----------|
| `cat <file>` | Displays entire file | Small files | N/A |
| `less <file>` | Views file page by page | Large files | Arrows, Q to quit |
| `more <file>` | Similar to less (older) | Alternative pager | Space, Q to quit |
| `head <file>` | Shows first 10 lines | Quick preview | `-n 20` (first 20) |
| `tail <file>` | Shows last 10 lines | Log files | `-f` (follow updates) |
| `tail -f <file>` | Follows file updates | Live log monitoring | Ctrl+C to stop |
| `wc <file>` | Counts lines, words, characters | File statistics | `-l` (lines only) |

---

## 🔍 File Search and Navigation

### Find Files

| Command | What It Does | Examples | Options |
|---------|-------------|----------|---------|
| `find <path> -name "<pattern>"` | Searches by name | `find ~ -name "*.pdf"` | Case-sensitive |
| `find <path> -iname "<pattern>"` | Case-insensitive search | `find . -iname "*.JPG"` | Ignores case |
| `find <path> -type f` | Finds files only | `find . -type f` | Excludes directories |
| `find <path> -type d` | Finds directories only | `find . -type d` | Excludes files |
| `find <path> -size +100M` | Finds files larger than 100MB | `find ~ -size +1G` | `+` (greater), `-` (smaller) |
| `find <path> -mtime -7` | Modified in last 7 days | `find . -mtime -1` | Recent files |

### Quick Search

| Command | What It Does | When to Use | Notes |
|---------|-------------|-------------|-------|
| `locate <pattern>` | Fast database search | Quick file finding | Run `sudo updatedb` first |
| `locate -i <pattern>` | Case-insensitive locate | Flexible searching | Searches pre-built index |
| `which <command>` | Finds command location | Check if installed | `which python3` |
| `whereis <command>` | Finds binary, source, manual | Complete command info | `whereis ls` |

---

## 🔐 File Permissions and Ownership

### Understanding Permissions

**Format**: `rwxrwxrwx` (owner, group, others)
- `r` (read) = 4
- `w` (write) = 2  
- `x` (execute) = 1

**Common Permission Values**:
- `644` - Regular files (rw-r--r--)
- `755` - Executables/directories (rwxr-xr-x)
- `700` - Private files (rwx------)
- `777` - Full access (not recommended!)

### Changing Permissions

| Command | What It Does | Examples | Notes |
|---------|-------------|----------|-------|
| `chmod 755 <file>` | Sets permissions numerically | `chmod 644 file.txt` | Owner: rwx, Group/Other: rx |
| `chmod u+x <file>` | Adds execute for user | `chmod u+x script.sh` | Makes script executable |
| `chmod g-w <file>` | Removes write for group | `chmod g-w doc.txt` | Group can't modify |
| `chmod o+r <file>` | Adds read for others | `chmod o+r public.txt` | Others can read |
| `chmod -R 755 <dir>` | Recursive permission change | `chmod -R 755 project/` | Changes dir and contents |

**Symbols**: `u` (user/owner), `g` (group), `o` (others), `a` (all)

### Changing Ownership

| Command | What It Does | When to Use | Examples |
|---------|-------------|-------------|----------|
| `sudo chown <user> <file>` | Changes file owner | Transfer ownership | `sudo chown john file.txt` |
| `sudo chown <user>:<group> <file>` | Changes owner and group | Complete ownership change | `sudo chown john:staff file.txt` |
| `sudo chown -R <user> <dir>` | Recursive ownership change | Directory trees | `sudo chown -R john project/` |
| `sudo chgrp <group> <file>` | Changes group only | Group reassignment | `sudo chgrp staff file.txt` |

### View Permissions

| Command | What It Does | Output |
|---------|-------------|--------|
| `ls -l <file>` | Shows permissions, owner, group | `-rw-r--r-- 1 user group 1024 Jan 1 file.txt` |
| `stat <file>` | Detailed file information | Includes octal permissions |

---

## 📝 Text Processing and Manipulation

### Grep (Search Text)

| Command | What It Does | Examples | Options |
|---------|-------------|----------|---------|
| `grep "<term>" <file>` | Searches for text in file | `grep "error" log.txt` | Basic search |
| `grep -i "<term>" <file>` | Case-insensitive search | `grep -i "Error" log.txt` | Ignores case |
| `grep -r "<term>" <dir>` | Recursive directory search | `grep -r "TODO" src/` | Searches all files |
| `grep -n "<term>" <file>` | Shows line numbers | `grep -n "error" log.txt` | With line numbers |
| `grep -v "<term>" <file>` | Inverts match (excludes) | `grep -v "debug" log.txt` | Shows non-matching lines |
| `grep -c "<term>" <file>` | Counts matches | `grep -c "error" log.txt` | Number of matches |
| `grep -A 3 "<term>" <file>` | Shows 3 lines after match | Context after | `-B 3` (before), `-C 3` (both) |

### Sed (Stream Editor)

| Command | What It Does | Examples | Notes |
|---------|-------------|----------|-------|
| `sed 's/old/new/' <file>` | Replaces first occurrence per line | `sed 's/cat/dog/' pets.txt` | Not saved |
| `sed 's/old/new/g' <file>` | Replaces all occurrences | `sed 's/cat/dog/g' pets.txt` | Global replace |
| `sed -i 's/old/new/g' <file>` | Replaces and saves | `sed -i 's/old/new/g' config.txt` | Edits in-place |
| `sed '/pattern/d' <file>` | Deletes matching lines | `sed '/^#/d' file.txt` | Removes comments |
| `sed -n '5,10p' <file>` | Prints lines 5-10 | `sed -n '1,5p' file.txt` | Range print |

### Awk (Text Processing)

| Command | What It Does | Examples | Notes |
|---------|-------------|----------|-------|
| `awk '{print $1}' <file>` | Prints first column | `awk '{print $1}' data.txt` | Space-delimited |
| `awk '{print $1,$3}' <file>` | Prints columns 1 and 3 | Multiple columns | Comma separates |
| `awk '$3 > 100' <file>` | Filters by condition | `awk '$2 == "active"' status.txt` | Conditional output |
| `awk -F: '{print $1}' <file>` | Custom delimiter | `awk -F: '{print $1}' /etc/passwd` | Colon delimiter |

### Sort and Unique

| Command | What It Does | Examples | Options |
|---------|-------------|----------|---------|
| `sort <file>` | Sorts lines alphabetically | `sort names.txt` | `-r` (reverse) |
| `sort -n <file>` | Numeric sort | `sort -n numbers.txt` | Sorts as numbers |
| `sort -k2 <file>` | Sorts by column 2 | `sort -k2 data.txt` | Column-based sorting |
| `sort <file> \| uniq` | Removes duplicate lines | Adjacent duplicates only | Sort first! |
| `sort <file> \| uniq -c` | Counts occurrences | `sort names.txt \| uniq -c` | With count |
| `sort <file> \| uniq -d` | Shows only duplicates | Find repeated lines | Must sort first |

### Cut (Extract Columns)

| Command | What It Does | Examples | Notes |
|---------|-------------|----------|-------|
| `cut -d: -f1 <file>` | Extracts field 1 | `cut -d: -f1,3 /etc/passwd` | Colon delimiter |
| `cut -c1-10 <file>` | Extracts characters 1-10 | `cut -c1-5 names.txt` | Character range |
| `cut -f2,4 <file>` | Extracts fields 2 and 4 | `cut -f2,4 data.txt` | Tab-delimited default |

---

## 📊 System Monitoring and Performance

### Real-Time Monitoring

| Command | What It Does | Key Controls | Install |
|---------|-------------|--------------|---------|
| `top` | Interactive process viewer | `q` (quit), `k` (kill), `M` (sort by memory), `P` (CPU) | Pre-installed |
| `htop` | Enhanced process viewer | Mouse support, F9 (kill), F6 (sort) | `sudo apt install htop` |
| `vmstat 2` | Virtual memory statistics | Updates every 2 seconds | Pre-installed |
| `iostat` | CPU and disk I/O stats | Shows disk performance | `sudo apt install sysstat` |
| `watch -n 2 <command>` | Repeats command every 2 seconds | `watch -n 1 free -h` | Pre-installed |

### Memory Monitoring

| Command | What It Does | When to Use | Options |
|---------|-------------|-------------|---------|
| `free -h` | Shows RAM and swap usage | Check memory availability | `-m` (MB), `-g` (GB) |
| `watch -n 2 free -h` | Live memory monitoring | Continuous updates | Updates every 2 seconds |

### Disk Usage

| Command | What It Does | Examples | Options |
|---------|-------------|----------|---------|
| `du -h <dir>` | Shows directory disk usage | `du -h Documents/` | Human-readable sizes |
| `du -sh <dir>` | Summary of directory size | `du -sh Downloads/` | Total size only |
| `du -h --max-depth=1` | Limits subdirectory depth | `du -h --max-depth=1 ~` | One level deep |
| `du -h \| sort -hr` | Largest directories first | Find space hogs | Sorted by size |
| `ncdu /` | Interactive disk analyzer | Explore disk usage | `sudo apt install ncdu` |

### System Logs

| Command | What It Does | When to Use | Options |
|---------|-------------|-------------|---------|
| `journalctl` | Views systemd journal logs | System troubleshooting | `-f` (follow) |
| `journalctl -f` | Follows log in real-time | Live monitoring | Like `tail -f` |
| `journalctl -u <service>` | Shows service logs | Specific service | `journalctl -u apache2` |
| `journalctl --since today` | Today's logs only | Recent events | Time-based filter |
| `dmesg` | Kernel ring buffer messages | Hardware/driver issues | Boot messages |
| `sudo tail -f /var/log/auth.log` | Authentication log | Login monitoring | Live updates |

---

## ⚙️ Process Management

### List Processes

| Command | What It Does | Output Details | Options |
|---------|-------------|----------------|---------|
| `ps aux` | Shows all processes | USER, PID, CPU%, MEM%, COMMAND | Full list |
| `ps ux` | Shows your processes | Current user only | Personal processes |
| `ps aux \| grep <name>` | Finds specific process | `ps aux \| grep firefox` | Search processes |
| `pstree` | Process tree view | Hierarchical display | Parent-child relationships |
| `top` | Real-time process list | Interactive, updates automatically | Press `q` to quit |

### Kill Processes

| Command | What It Does | When to Use | Signal |
|---------|-------------|-------------|--------|
| `kill <PID>` | Terminates process gracefully | Normal process ending | TERM (15) |
| `kill -9 <PID>` | Forces immediate termination | Unresponsive processes | KILL (9) |
| `killall <name>` | Kills all matching processes | `killall firefox` | By name |
| `pkill <pattern>` | Kills processes by pattern | `pkill -i chrome` | Pattern matching |
| `pkill -u <user>` | Kills user's processes | All processes by user | User-based |

**Finding PIDs**: Use `ps aux | grep <process>` or `pidof <process>`

### Background and Foreground

| Command | What It Does | When to Use | Keys |
|---------|-------------|-------------|------|
| `<command> &` | Runs command in background | Long-running tasks | Append `&` |
| `jobs` | Lists background jobs | View running jobs | Shows job numbers |
| `fg %1` | Brings job 1 to foreground | Resume interactive work | Use job number |
| `bg %1` | Continues job 1 in background | Resume suspended job | After Ctrl+Z |
| `Ctrl+Z` | Suspends current process | Pause running program | Then use `bg` |
| `disown` | Detaches job from shell | Keep running after logout | After backgrounding |

### Process Priority

| Command | What It Does | Priority Range | Notes |
|---------|-------------|----------------|-------|
| `nice -n 10 <command>` | Starts with priority | -20 (highest) to 19 (lowest) | Higher number = lower priority |
| `renice -n 5 -p <PID>` | Changes running process priority | Same range | Requires appropriate permissions |

---

## 🌐 Network Operations

### Network Configuration

| Command | What It Does | When to Use | Alternative |
|---------|-------------|-------------|-------------|
| `ip addr show` | Shows IP addresses | Check network config | `ip a` (short) |
| `ip route show` | Displays routing table | View network routes | `ip r` (short) |
| `ifconfig` | Legacy network info | Older systems | `sudo apt install net-tools` |
| `ip link show` | Shows network interfaces | Check interface status | Interface details |

### Network Connectivity

| Command | What It Does | Examples | Options |
|---------|-------------|----------|---------|
| `ping <host>` | Tests connectivity | `ping google.com` | `-c 4` (4 packets) |
| `ping -c 4 <host>` | Sends 4 packets and stops | `ping -c 10 8.8.8.8` | Limited ping |
| `traceroute <host>` | Shows network path | `traceroute google.com` | `sudo apt install traceroute` |
| `nslookup <domain>` | DNS lookup | `nslookup google.com` | Basic DNS query |
| `dig <domain>` | Detailed DNS query | `dig google.com` | `sudo apt install dnsutils` |
| `host <domain>` | Simple DNS lookup | `host google.com` | Quick DNS check |

### Network Monitoring

| Command | What It Does | Install | Usage |
|---------|-------------|---------|-------|
| `netstat -tuln` | Shows listening ports | `sudo apt install net-tools` | `-t` (TCP), `-u` (UDP), `-l` (listening), `-n` (numeric) |
| `ss -tuln` | Modern netstat alternative | Pre-installed | Faster, more detailed |
| `ss -tulnp` | Shows process using port | Need root | Includes program names |
| `sudo iftop` | Bandwidth by connection | `sudo apt install iftop` | Real-time bandwidth |
| `nload` | Network traffic monitor | `sudo apt install nload` | Visual bandwidth graph |
| `nethogs` | Bandwidth by process | `sudo apt install nethogs` | Shows which app uses bandwidth |

### Download Files

| Command | What It Does | Examples | Options |
|---------|-------------|----------|---------|
| `wget <url>` | Downloads files | `wget https://example.com/file.zip` | `-c` (continue), `-O` (rename) |
| `wget -c <url>` | Resumes interrupted download | Continue download | Auto-resume |
| `curl -O <url>` | Downloads file | `curl -O https://example.com/file.zip` | `-L` (follow redirects) |
| `curl -o <name> <url>` | Downloads as specified name | `curl -o file.zip <url>` | Custom filename |

### Firewall (UFW)

| Command | What It Does | Examples | Notes |
|---------|-------------|----------|-------|
| `sudo ufw status` | Shows firewall status | Check if enabled | Shows rules |
| `sudo ufw enable` | Activates firewall | Enable protection | Enables rules |
| `sudo ufw disable` | Deactivates firewall | Temporarily disable | Not recommended |
| `sudo ufw allow 80/tcp` | Opens port 80 | `sudo ufw allow 22/tcp` | Web server |
| `sudo ufw deny 23/tcp` | Blocks port 23 | Block telnet | Security |
| `sudo ufw allow from 192.168.1.0/24` | Allows IP range | Allow subnet | Network-based |
| `sudo ufw delete allow 80/tcp` | Removes rule | Delete existing rule | Rule management |

---

## 💾 Disk and Storage Management

### Disk Information

| Command | What It Does | When to Use | Options |
|---------|-------------|-------------|---------|
| `lsblk` | Shows all storage devices and partitions in tree format | View disk structure | `-f` (show filesystems) |
| `df -h` | Displays disk space usage for all mounted filesystems | Check free space | `-T` (show filesystem type) |
| `sudo fdisk -l` | Lists all disks and partitions with detailed information | Detailed disk info | Shows partition table |

### Mounting and Unmounting

| Command | What It Does | Examples | Notes |
|---------|-------------|----------|-------|
| `sudo mount /dev/sdb1 /mnt/usb` | Mounts a partition to specified directory | Mount USB drive | Create mount point first |
| `sudo umount /mnt/usb` | Unmounts a mounted filesystem | Safely remove device | Must not be in use |
| `mount \| grep ^/dev` | Lists currently mounted devices | Check what's mounted | Shows active mounts |

### Partition Management

| Command | What It Does | When to Use | Warning |
|---------|-------------|-------------|---------|
| `sudo fdisk /dev/sdb` | Interactive partition editor | Create, delete, modify partitions | ⚠️ Can destroy data! |
| `sudo gparted` | Graphical partition editor | GUI partitioning | `sudo apt install gparted` |

### Check Disk Health

| Command | What It Does | When to Use | Install/Warning |
|---------|-------------|-------------|-----------------|
| `sudo fsck /dev/sdb1` | Checks and repairs filesystem | Fix filesystem errors | ⚠️ Only on unmounted filesystems |
| `sudo smartctl -a /dev/sda` | Shows disk health status | Monitor disk health | `sudo apt install smartmontools` |

---

## 👥 User and Group Management

### User Operations

| Command | What It Does | Examples | Notes |
|---------|-------------|----------|-------|
| `sudo adduser <username>` | Creates new user with home directory | `sudo adduser john` | Interactive setup |
| `sudo deluser <username>` | Removes user account | `sudo deluser john` | `--remove-home` to delete home dir |
| `passwd` | Changes password for current user | Change your password | Interactive prompts |
| `sudo passwd <username>` | Changes another user's password | `sudo passwd john` | Admin privilege required |
| `su - <username>` | Switches to another user account | `su - john` | Full login environment |
| `sudo -u <username> <cmd>` | Runs command as specified user | `sudo -u www-data ls /var/www` | Execute as different user |

### Group Operations

| Command | What It Does | Examples | Notes |
|---------|-------------|----------|-------|
| `sudo groupadd <group>` | Creates new group | `sudo groupadd developers` | System group creation |
| `sudo usermod -aG <group> <user>` | Adds user to supplementary group | `sudo usermod -aG sudo john` | `-a` appends, `-G` specifies groups |
| `sudo deluser <user> <group>` | Removes user from specified group | `sudo deluser john sudo` | Group membership removal |
| `groups <username>` | Shows all groups user belongs to | `groups john` | List user's groups |

### User Information

| Command | What It Does | Output | When to Use |
|---------|-------------|--------|-------------|
| `whoami` | Displays current username | Your username | Quick identity check |
| `who` | Lists all currently logged-in users | Users and login times | See who's logged in |
| `id <username>` | Shows user ID, group ID, and groups | UID, GID, group list | Detailed user info |

---

## 🔧 System Services

Zorin OS uses **systemd** for service management.

### Service Control

| Command | What It Does | Examples | When to Use |
|---------|-------------|----------|-------------|
| `sudo systemctl start <service>` | Starts a service | `sudo systemctl start apache2` | Start stopped service |
| `sudo systemctl stop <service>` | Stops a running service | `sudo systemctl stop apache2` | Stop running service |
| `sudo systemctl restart <service>` | Stops and then starts a service | `sudo systemctl restart nginx` | Apply config changes |
| `sudo systemctl reload <service>` | Reloads configuration without stopping | `sudo systemctl reload nginx` | Update config without downtime |

### Service Status

| Command | What It Does | Output | When to Use |
|---------|-------------|--------|-------------|
| `sudo systemctl status <service>` | Shows detailed status of a service | Active/inactive, recent logs | Troubleshoot service issues |
| `systemctl is-active <service>` | Returns active/inactive status | Simple yes/no | Quick status check |
| `systemctl is-enabled <service>` | Returns enabled/disabled status | enabled/disabled | Check boot configuration |

### Enable/Disable Services

| Command | What It Does | Examples | Purpose |
|---------|-------------|----------|---------|
| `sudo systemctl enable <service>` | Configures service to start at boot | `sudo systemctl enable apache2` | Auto-start on boot |
| `sudo systemctl disable <service>` | Prevents service from starting at boot | `sudo systemctl disable apache2` | Don't auto-start |
| `sudo systemctl enable --now <service>` | Enables and starts service immediately | `sudo systemctl enable --now nginx` | Enable + start in one command |

### List Services

| Command | What It Does | When to Use | Output |
|---------|-------------|-------------|--------|
| `systemctl list-units --type=service` | Shows all loaded services | View all services | Complete service list |
| `systemctl list-units --type=service --state=running` | Shows only running services | See active services | Running services only |
| `systemctl --failed` | Shows services that failed to start | Troubleshoot boot issues | Failed services |

---

## 🗜️ Compression and Archives

### Tar Archives

| Command | What It Does | Options Explained | Examples |
|---------|-------------|-------------------|----------|
| `tar -cvf archive.tar directory/` | Creates uncompressed tar archive | `-c` create, `-v` verbose, `-f` filename | Basic archive |
| `tar -czvf archive.tar.gz directory/` | Creates gzip-compressed archive | `-z` gzip compression | Most common format |
| `tar -cjvf archive.tar.bz2 directory/` | Creates bzip2-compressed archive | `-j` bzip2 (better compression) | Smaller size, slower |
| `tar -xvf archive.tar` | Extracts tar archive | `-x` extract | Unpack archive |
| `tar -xzvf archive.tar.gz` | Extracts gzip-compressed archive | Auto-detects compression | Extract .tar.gz |
| `tar -tvf archive.tar` | Lists files without extracting | `-t` list contents | Preview archive |
| `tar -xzvf archive.tar.gz -C /path/` | Extracts to specific directory | `-C` change directory | Extract to location |

### Zip Archives

| Command | What It Does | Examples | Options |
|---------|-------------|----------|---------|
| `zip -r archive.zip directory/` | Creates zip archive | `zip -r backup.zip ~/Documents` | `-r` recursive |
| `unzip archive.zip` | Extracts zip archive | `unzip backup.zip` | Extract to current dir |
| `unzip -l archive.zip` | Lists files without extracting | Preview contents | `-l` list only |
| `unzip archive.zip -d /path/` | Extracts to specific directory | `unzip file.zip -d ~/Desktop` | `-d` destination |

### Gzip (Individual Files)

| Command | What It Does | Behavior | Options |
|---------|-------------|----------|---------|
| `gzip filename.txt` | Compresses file | Creates .gz, removes original | Default behavior |
| `gunzip filename.txt.gz` | Decompresses file | Restores original, removes .gz | Decompress |
| `gzip -k filename.txt` | Compresses while keeping original | Keeps both files | `-k` keep original |
| `gzip -d filename.txt.gz` | Alternative decompress | Same as gunzip | `-d` decompress |

---

## 🛠️ System Maintenance

### System Updates

| Command | What It Does | When to Use | Frequency |
|---------|-------------|-------------|-----------|
| `sudo apt update && sudo apt upgrade -y && sudo apt autoremove -y` | Complete update routine | System maintenance | Weekly |

### Disk Cleanup

| Command | What It Does | Space Saved | When to Use |
|---------|-------------|-------------|-------------|
| `sudo apt clean && sudo apt autoclean` | Removes old package files | Several GB | Monthly cleanup |
| `sudo apt autoremove --purge` | Removes unused kernels and packages | 500MB - 2GB | After kernel updates |
| `rm -rf ~/.cache/thumbnails/*` | Clears thumbnail cache | 100MB - 500MB | Visual cache cleanup |
| `sudo journalctl --vacuum-time=7d` | Keeps only last 7 days of logs | Varies | Log management |

### Check System Issues

| Command | What It Does | When to Use | Purpose |
|---------|-------------|-------------|---------|
| `sudo apt check` | Checks for broken dependencies | After failed install | Verify package integrity |
| `sudo apt --fix-broken install` | Fixes broken package dependencies | Installation problems | Repair packages |
| `sudo dpkg --configure -a` | Configures unpacked packages | Interrupted installs | Complete configuration |

### Scheduled Tasks (Cron)

| Command | What It Does | When to Use | Editor |
|---------|-------------|-------------|--------|
| `crontab -e` | Opens crontab editor for user | Schedule personal tasks | Opens default editor |
| `crontab -l` | Lists scheduled cron jobs | View scheduled tasks | Shows current crontab |
| `sudo nano /etc/crontab` | Edits system-wide cron jobs | System-level scheduling | System crontab |

**Cron Format**: `minute hour day month weekday command`  
**Example**: `0 2 * * * /path/to/script.sh` (runs at 2 AM daily)

---

## 🐚 Shell Utilities

### Command History

| Command | What It Does | Examples | Shortcuts |
|---------|-------------|----------|-----------|
| `history` | Lists previously executed commands | View command history | Shows numbered list |
| `history \| grep <term>` | Searches command history | `history \| grep apt` | Find past commands |
| `!123` | Re-runs command number 123 | Execute by number | From history list |
| `!!` | Repeats last command | `sudo !!` (run last as root) | Quick repeat |
| `!$` | Uses last argument | `ls file.txt` then `cat !$` | Last argument shortcut |
| `history -c` | Clears command history | Privacy/cleanup | Removes all history |

### Aliases

| Command | What It Does | Examples | Notes |
|---------|-------------|----------|-------|
| `alias ll='ls -lah'` | Creates command shortcut | `alias update='sudo apt update'` | Current session only |
| `alias` | Shows all defined aliases | View active aliases | Lists all shortcuts |
| `unalias ll` | Removes an alias | `unalias update` | Delete alias |
| `echo "alias ll='ls -lah'" >> ~/.bashrc` | Makes alias permanent | Add to bashrc | Edit config file |
| `source ~/.bashrc` | Reloads bash configuration | Apply changes | Reload without restart |

**Common Useful Aliases**:
```bash
alias update='sudo apt update && sudo apt upgrade -y'
alias clean='sudo apt autoremove && sudo apt autoclean'
alias ll='ls -lah'
alias ..='cd ..'
alias ...='cd ../..'
```

### Environment Variables

| Command | What It Does | Examples | Scope |
|---------|-------------|----------|-------|
| `env` | Lists all environment variables | View all variables | Current environment |
| `echo $PATH` | Displays specific variable value | `echo $HOME` | Variable content |
| `export VAR="value"` | Sets temporary variable | `export EDITOR=nano` | Current session |
| `echo 'export VAR="value"' >> ~/.bashrc` | Sets permanent variable | Add to bashrc | All future sessions |
| `source ~/.bashrc` | Reloads bash configuration | Apply changes | Reload environment |

**Common Variables**: `$PATH`, `$HOME`, `$USER`, `$SHELL`, `$PWD`

### Redirection and Pipes

| Command | What It Does | Examples | Symbol Meaning |
|---------|-------------|----------|----------------|
| `command > file.txt` | Redirects output to file (overwrites) | `ls > files.txt` | `>` overwrite |
| `command >> file.txt` | Appends output to file | `echo "text" >> log.txt` | `>>` append |
| `command 2> errors.txt` | Redirects errors to file | `make 2> errors.log` | `2>` stderr only |
| `command &> all.txt` | Redirects output and errors | `script.sh &> output.log` | `&>` both streams |
| `command1 \| command2` | Pipes output to another command | `ls \| grep ".txt"` | `\|` pipe |
| `command < input.txt` | Uses file as input | `sort < names.txt` | `<` input redirect |
| `command \| tee file.txt` | Saves output and displays it | `ls \| tee list.txt` | View and save |

**Common Pipe Combinations**:
```bash
ps aux | grep nginx          # Find process
history | grep apt           # Search history
cat file.txt | sort | uniq  # Sort and remove duplicates
df -h | grep /dev/sda       # Filter disk info
```
