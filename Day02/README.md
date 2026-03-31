# Linux Administration Basics

This project explains the basic concepts of Linux system administration including SSH, Package Management, User Management, and File Permissions. These are essential skills for working with Linux systems.

---

## Table of Contents
- SSH (Secure Shell)
- Package Management
- User Management
- File Permissions
- Conclusion

---

## SSH (Secure Shell)

SSH (Secure Shell) is a protocol used to securely connect to a remote computer over a network. It encrypts the communication between the client and server to ensure safe access.

### Features
- Secure remote login
- Encrypted communication
- Remote command execution
- Secure file transfer using SCP or SFTP

### Basic SSH Command

ssh username@server_ip

Example:

ssh user@192.168.1.10

### Common SSH Commands

ssh user@host – Connect to a remote server  
ssh-keygen – Generate SSH keys  
ssh-copy-id user@host – Copy public key to remote server  
scp file user@host:/path – Securely copy files  

---

## Package Management

Package management is used to install, update, remove, and manage software packages in Linux systems.

### Common Package Managers

Ubuntu / Debian – apt  
Fedora / RHEL – dnf / yum  
Arch Linux – pacman  

### Basic APT Commands

Update package list

sudo apt update

Upgrade installed packages

sudo apt upgrade

Install a package

sudo apt install package_name

Remove a package

sudo apt remove package_name

Search for a package

apt search package_name

---

## User Management

Linux supports multiple users, allowing administrators to control system access.

### Create a User

sudo useradd username

Create user with home directory

sudo useradd -m username

Set a password

sudo passwd username

### Delete a User

sudo userdel username

Delete a user along with home directory

sudo userdel -r username

### Important User Files

/etc/passwd – Stores user account information  
/etc/shadow – Stores encrypted passwords  
/etc/group – Stores group information  

### Add User to a Group

sudo usermod -aG groupname username

Example:

sudo usermod -aG sudo user

---

## File Permissions

Linux uses file permissions to control access to files and directories.

Each file has permissions for:
- Owner
- Group
- Others

### Permission Types

r – Read  
w – Write  
x – Execute  

### Example Permission

-rwxr-xr--

Owner – Read, Write, Execute  
Group – Read, Execute  
Others – Read only  

### View File Permissions

ls -l

Example output

-rw-r--r-- 1 user user 1024 file.txt

### Change File Permissions

chmod 755 file.sh

chmod u+x file.sh

### Change File Ownership

sudo chown user:group filename

Example:

sudo chown john:developers project.txt

---

## Conclusion

Understanding SSH, package management, user management, and file permissions is important for Linux system administration. These tools help administrators manage systems, control user access, and maintain security.
