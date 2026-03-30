# Linux Basics and Common Commands

## Introduction

Linux is an open-source operating system widely used in servers, programming, cybersecurity, and software development. Unlike some operating systems that rely heavily on graphical interfaces, Linux allows users to interact with the system using a command-line interface called the **Terminal**.

Linux is known for its stability, security, and flexibility. It is free to use and has many different versions called **distributions (distros)**.

---

## Popular Linux Distributions

Some commonly used Linux distributions include:

* Ubuntu
* Kali Linux
* Debian
* Fedora

Each distribution is designed for different purposes such as general use, development, or cybersecurity.

---

## Linux File System Basics

In Linux, folders are called **directories**. The file system is organized into different directories that store system files, user files, and configuration data.

Important directories:

```
/home   → User files and personal directories
/root   → Root (administrator) user files
/etc    → System configuration files
/bin    → Essential system commands
/tmp    → Temporary files
```

---

## Basic Linux Commands

### 1. pwd

Displays the current working directory.

```
pwd
```

Example output:

```
/home/user
```

---

### 2. ls

Lists the files and directories in the current directory.

```
ls
```

Useful options:

```
ls -l   # detailed list
ls -a   # show hidden files
```

---

### 3. cd

Changes the current directory.

```
cd foldername
```

Example:

```
cd Documents
```

To move back one directory:

```
cd ..
```

---

### 4. mkdir

Creates a new directory.

```
mkdir testfolder
```

---

### 5. touch

Creates a new empty file.

```
touch file.txt
```

---

### 6. cp

Copies files from one location to another.

```
cp file.txt backup.txt
```

---

### 7. mv

Moves or renames files.

```
mv file.txt newfile.txt
```

---

### 8. rm

Deletes files.

```
rm file.txt
```

To delete a directory:

```
rm -r foldername
```

---

### 9. cat

Displays the content of a file.

```
cat file.txt
```

---

### 10. clear

Clears the terminal screen.

```
clear
```

---

## Useful Linux Shortcuts

```
Tab       → Auto-complete commands and filenames
Ctrl + C  → Stop a running process
Ctrl + L  → Clear the terminal screen
```

---

## Installing Packages (Ubuntu / Kali Linux)

To install software in many Linux distributions, the **apt package manager** is used.

Update package list:

```
sudo apt update
```

Install a package:

```
sudo apt install packagename
```

Example:

```
sudo apt install git
```

---

## Beginner Practice Commands

You can practice basic Linux commands with the following sequence:

```
pwd
ls
mkdir test
cd test
touch file.txt
ls
cat file.txt
```

This simple exercise helps you understand directory navigation, file creation, and file viewing in Linux.

---

## Conclusion

Learning basic Linux commands is the first step toward mastering Linux. These commands help users manage files, navigate directories, and control the system efficiently through the terminal.

With regular practice, working in the Linux command line becomes faster and more powerful than using graphical interfaces.

