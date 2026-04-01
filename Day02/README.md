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

# LVM (Logical Volume Manager) in Linux

Logical Volume Manager (LVM) is a storage management system used in Linux that provides flexible disk management. It allows administrators to combine multiple disks, resize storage, and manage volumes efficiently compared to traditional disk partitioning.

---

## LVM Architecture

LVM works with three main components:

Physical Disk → Physical Volume (PV) → Volume Group (VG) → Logical Volume (LV) → File System

Example:

/dev/sdb → PV → VG (vg_data) → LV (lv_data) → Mounted to /data

---

## 1. Physical Volume (PV)

A Physical Volume is a disk or partition used by LVM.

Create a Physical Volume:

pvcreate /dev/sdb

Display Physical Volume information:

pvdisplay

---

## 2. Volume Group (VG)

A Volume Group is created by combining one or more Physical Volumes. It acts as a storage pool.

Create a Volume Group:

vgcreate vg_data /dev/sdb

Display Volume Group details:

vgdisplay

Extend Volume Group by adding another disk:

vgextend vg_data /dev/sdc

---

## 3. Logical Volume (LV)

Logical Volumes are created from the free space in a Volume Group and behave like normal disk partitions.

Create a Logical Volume:

lvcreate -L 5G -n lv_data vg_data

Display Logical Volume information:

lvdisplay

---

## Create File System

Format the Logical Volume:

mkfs.ext4 /dev/vg_data/lv_data

---

## Mount Logical Volume

Create a directory:

mkdir /data

Mount the logical volume:

mount /dev/vg_data/lv_data /data

Check disk usage:

df -h

---

## Extend Logical Volume

Increase the Logical Volume size:

lvextend -L +2G /dev/vg_data/lv_data

Resize the filesystem:

resize2fs /dev/vg_data/lv_data

---

## Reduce Logical Volume

First reduce the filesystem:

resize2fs /dev/vg_data/lv_data 3G

Then reduce the logical volume:

lvreduce -L 3G /dev/vg_data/lv_data

Note: Always reduce the filesystem before reducing the logical volume to avoid data loss.

---

## LVM Snapshot

Create snapshot:

lvcreate -L 1G -s -n lv_snapshot /dev/vg_data/lv_data

Snapshots are useful for backups and testing.

---

## Important LVM Commands

pvcreate – Create Physical Volume  
pvdisplay – Display Physical Volume details  
vgcreate – Create Volume Group  
vgdisplay – Display Volume Group details  
lvcreate – Create Logical Volume  
lvdisplay – Display Logical Volume details  
lvextend – Extend Logical Volume  
lvreduce – Reduce Logical Volume  

---

## Advantages of LVM

- Flexible storage management
- Easy disk resizing
- Combine multiple disks
- Snapshot support
- Efficient disk utilization

---

## Conclusion

Understanding SSH, package management, user management, file permissions and LVM management is important for Linux system administration. These tools help administrators manage systems, control user access, and maintain security.
