# 🐧 Linux Commands for DevOps

![Linux](https://img.shields.io/badge/Linux-Commands-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![DevOps](https://img.shields.io/badge/DevOps-Learning-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Shell](https://img.shields.io/badge/Shell-Scripting-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)

> 📚 A practical Linux command reference for **DevOps beginners**, covering everyday commands used while working with servers, logs, processes, networking, permissions, and troubleshooting.

---

## 📌 Table of Contents

- [🎯 Purpose](#-purpose)
- [📂 File & Directory Basics](#-file--directory-basics)
- [📄 File Viewing](#-file-viewing)
- [📋 File & Directory Management](#-file--directory-management)
- [🔎 Search & Text Processing](#-search--text-processing)
- [🔀 Pipes & Redirection](#-pipes--redirection)
- [🖥️ System Information](#️-system-information)
- [💻 Memory, Disk & Storage](#-memory-disk--storage)
- [⚙️ Process Management](#️-process-management)
- [🔧 Services & Systemd](#-services--systemd)
- [🌐 Networking](#-networking)
- [📡 Network Troubleshooting](#-network-troubleshooting)
- [🔐 Remote Access](#-remote-access)
- [🛡️ Permissions & Ownership](#️-permissions--ownership)
- [🚀 DevOps Quick Reference](#-devops-quick-reference)
- [📖 Learning Path](#-learning-path)

---

## 🎯 Purpose

This repository is my **Linux command reference while learning DevOps**.

The commands are organized around practical tasks commonly performed on Linux servers, including:

- 📁 Navigating directories
- 📄 Working with files
- 🔍 Searching logs and text
- 📊 Checking CPU, memory, and disk usage
- ⚙️ Managing processes and services
- 🌐 Troubleshooting network connectivity
- 🔐 Connecting to remote servers
- 🛡️ Managing permissions and ownership

---

# 📂 File & Directory Basics

### `pwd` — Present Working Directory

Shows the current directory.

```bash
pwd
```

### `ls` — List Files and Directories

```bash
ls
ls -l
ls -a
ls -h
ls -la
```

| Command | Purpose |
|---|---|
| `ls` | List files and directories |
| `ls -l` | Detailed listing |
| `ls -a` | Show hidden files |
| `ls -h` | Human-readable sizes |
| `ls -la` | Detailed listing including hidden files |

### `cd` — Change Directory

```bash
cd /var/log
cd ..
cd ~
cd -
```

| Command | Purpose |
|---|---|
| `cd /var/log` | Go to a specific directory |
| `cd ..` | Go one directory back |
| `cd ~` | Go to the home directory |
| `cd -` | Go to the previous directory |

### `mkdir` — Create Directory

```bash
mkdir devops
```

### `touch` — Create Empty File

```bash
touch notes.txt
```

---

# 📄 File Viewing

### `cat`

Displays file contents.

```bash
cat file.txt
```

### `less`

Reads large files without dumping the entire file onto the terminal.

```bash
less application.log
```

> 💡 Particularly useful when working with large application logs.

### `head`

Shows the beginning of a file or output.

```bash
head application.log
head -n 10 application.log
```

### `tail`

Shows the ending of a file or output.

```bash
tail application.log
```

### ⭐ Real-Time Log Monitoring

```bash
tail -f application.log
```

This continuously displays new log entries as they are written.

> 🚀 **DevOps Tip:** `tail -f` is one of the most useful commands for monitoring application logs in real time.

---

# 📋 File & Directory Management

### `cp` — Copy

Copies files or directories.

```bash
cp source.txt backup.txt
```

### `mv` — Move / Rename

Moves or renames files and directories.

```bash
mv old.txt new.txt
mv file.txt /tmp/
```

### `rm` — Remove

Deletes files and directories.

```bash
rm file.txt
```

> ⚠️ Be careful with `rm` because deleted files may not be recoverable.

---

# 🔎 Search & Text Processing

These commands are especially useful when troubleshooting logs and processing server output.

| Command | Purpose |
|---|---|
| `find` | Find files and directories |
| `grep` | Search inside files |
| `wc` | Count lines, words, characters, and bytes |
| `sort` | Organize text/input |
| `uniq` | Filter adjacent duplicate lines |
| `cut` | Extract specific fields/sections |
| `awk` | Search, filter, and manipulate structured data |
| `sed` | Search and replace text |
| `\|` | Send output from one command to another |

### `find`

```bash
find /var/log -name "*.log"
```

### `grep`

Search for specific text.

```bash
grep "ERROR" application.log
```

### `wc`

```bash
wc -l application.log
```

### `sort`

```bash
sort names.txt
```

### `uniq`

```bash
sort names.txt | uniq
```

### `cut`

```bash
cut -d ":" -f 1 /etc/passwd
```

### `awk`

```bash
awk '{print $1}' file.txt
```

### `sed`

Used to search and replace text.

```bash
sed 's/old/new/g' file.txt
```

### 🔥 Combine Commands with Pipe

```bash
cat application.log | grep "ERROR"
```

The output of one command becomes the input of another.

---

# 🔀 Pipes & Redirection

Linux allows command output to be redirected or passed between commands.

| Operator | Purpose |
|---|---|
| `>` | Overwrite output to a file |
| `>>` | Append output to a file |
| `<` | Take input from a file |
| `\|` | Send output to another command |

### Overwrite

```bash
ls > files.txt
```

### Append

```bash
date >> system.log
```

### Pipe

```bash
ps -ef | grep java
```

> 💡 Pipes are extremely important for Linux troubleshooting and DevOps automation.

---

# 🖥️ System Information

| Command | Purpose |
|---|---|
| `date` | Display date |
| `uname` | Show Linux/kernel information |
| `hostname` | Show server name |
| `cat /etc/os-release` | Show OS information |
| `uptime` | Show uptime, users, and load average |
| `whoami` | Show current user |

### Examples

```bash
date
uname -a
hostname
cat /etc/os-release
uptime
whoami
```

> ☁️ These commands are useful when working on Linux/EC2 servers and checking the current server environment.

---

# 💻 Memory, Disk & Storage

### `free`

Checks memory usage.

```bash
free -h
```

### `df`

Checks filesystem/disk usage.

```bash
df -h
```

### `du`

Checks directory/file size.

```bash
du -h
```

A common combination:

```bash
du -sh /var/log
```

### 🚨 Quick Troubleshooting

```bash
free -h
df -h
du -sh /var/log
```

Use these when investigating memory or disk-space issues on a Linux server.

---

# ⚙️ Process Management

### `ps`

Shows running processes.

```bash
ps
ps -ef
```

### `top`

Shows real-time:

- CPU usage
- Memory usage
- Running processes
- System load

```bash
top
```

### `kill`

Terminates a process.

```bash
kill <PID>
```

> 🔍 Typical troubleshooting flow: identify the process with `ps` or `top`, then terminate it with `kill` when appropriate.

---

# 🔧 Services & Systemd

Linux services can be managed through `systemd`.

### Common Service Operations

```bash
systemctl start <service>
systemctl stop <service>
systemctl restart <service>
systemctl enable <service>
systemctl disable <service>
```

### Example

```bash
systemctl status nginx
systemctl restart nginx
```

> ⚠️ The uploaded notes refer to this area as `system` for service operations; the standard command used on systemd-based Linux systems is `systemctl`.

---

# 🌐 Networking

### `ip addr`

Shows IP addresses.

```bash
ip addr
```

### `ip route`

Shows routing information.

```bash
ip route
```

### `ping`

Checks network connectivity.

```bash
ping google.com
```

### `curl`

Useful for checking HTTP connectivity/status.

```bash
curl -I https://example.com
```

### `wget`

Downloads files.

```bash
wget https://example.com/file.zip
```

### `ss`

Checks listening ports and network sockets.

```bash
ss -tuln
```

---

# 📡 Network Troubleshooting

### `nslookup`

Checks DNS resolution.

```bash
nslookup example.com
```

### `dig`

Provides detailed DNS information.

```bash
dig example.com
```

### 🔥 Basic Troubleshooting Flow

```text
Application URL
      ↓
     curl
      ↓
   DNS Check
      ↓
  nslookup / dig
      ↓
 Network Check
      ↓
 ping / ip route
      ↓
 Port Check
      ↓
    ss -tuln
```

---

# 🔐 Remote Access

### `ssh`

Connect to a remote server.

```bash
ssh username@server-ip
```

### `scp`

Copy files between local and remote systems.

```bash
scp file.txt username@server-ip:/tmp/
```

> ☁️ These commands are commonly used when connecting to Linux servers such as AWS EC2 instances.

---

# 🛡️ Permissions & Ownership

### `chmod`

Changes file and directory permissions.

```bash
chmod 755 script.sh
```

### `chown`

Changes file ownership or group.

```bash
chown user:group file.txt
```

### Common Permission Concept

```text
r = read
w = write
x = execute
```

Example:

```text
-rwxr-xr-x
```

---

# 🚀 DevOps Quick Reference

## 🔍 Check Server

```bash
hostname
whoami
uptime
uname -a
```

## 💾 Check Disk

```bash
df -h
du -sh *
```

## 🧠 Check Memory

```bash
free -h
```

## ⚙️ Check Processes

```bash
ps -ef
top
```

## 📜 Check Logs

```bash
tail -f application.log
grep "ERROR" application.log
```

## 🌐 Check Application

```bash
curl -I http://localhost:8080
```

## 🔌 Check Ports

```bash
ss -tuln
```

## 🔐 Connect to Server

```bash
ssh username@server-ip
```

## 📦 Copy File to Server

```bash
scp file.txt username@server-ip:/tmp/
```

---

# 🧰 Common DevOps Troubleshooting Example

### Scenario: Application is not responding

Start with basic checks:

```bash
# 1. Check server
hostname
uptime

# 2. Check memory
free -h

# 3. Check disk
df -h

# 4. Check processes
top
ps -ef

# 5. Check application logs
tail -f application.log
grep "ERROR" application.log

# 6. Check application port
ss -tuln

# 7. Check HTTP response
curl -I http://localhost:8080
```

This provides a simple starting point for identifying whether the issue is related to **server resources, processes, logs, ports, or application connectivity**.

---

# 📖 Learning Path

### 🟢 Beginner

- [x] `pwd`
- [x] `ls`
- [x] `cd`
- [x] `mkdir`
- [x] `touch`
- [x] `cat`
- [x] `less`
- [x] `head`
- [x] `tail`

### 🟡 Intermediate

- [x] `cp`
- [x] `mv`
- [x] `rm`
- [x] `find`
- [x] `grep`
- [x] `wc`
- [x] `sort`
- [x] `uniq`
- [x] `cut`
- [x] `awk`
- [x] `sed`
- [x] Pipes & Redirection

### 🔴 DevOps Operations

- [x] `free`
- [x] `df`
- [x] `du`
- [x] `ps`
- [x] `top`
- [x] `kill`
- [x] `systemctl`
- [x] `ip`
- [x] `curl`
- [x] `ss`
- [x] `nslookup`
- [x] `dig`
- [x] `ssh`
- [x] `scp`
- [x] `chmod`
- [x] `chown`

---

## ⭐ Why Linux Matters in DevOps

Linux is a fundamental skill for DevOps engineers because many workloads, application servers, containers, CI/CD tools, and cloud environments run on Linux.

> 💡 **Practice every command on a Linux VM and understand the output instead of only memorizing the syntax.**

---

## 📚 Source Notes

This README was organized from my Linux learning notes, covering Linux basics, file operations, text processing, system information, resource monitoring, process management, networking, remote access, and permissions. fileciteturn0file0L1-L8

---

## 👨‍💻 Learning DevOps

This repository is part of my journey to build strong practical skills in:

```text
Linux
  ↓
Git & GitHub
  ↓
AWS
  ↓
Shell Scripting
  ↓
Docker
  ↓
Jenkins
  ↓
Kubernetes
  ↓
Terraform
  ↓
CI/CD
```

**Keep learning. Keep practicing. Keep automating. 🚀**
