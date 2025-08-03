# Linux-access-control-project

## Overview

This project explores the core access control mechanisms available in Linux operating systems. It demonstrates how to manage file and directory permissions using standard user/group settings, apply special file attributes like `setuid`, `setgid`, and the sticky bit, and enforce fine-grained access control through Access Control Lists (ACLs). Each section includes hands-on examples using essential Linux commands.

---

## 1. User and Group Permissions

Linux file systems assign permissions to three classes:
- **Owner**
- **Group**
- **Others**

Each class can have:
- `r` (read)
- `w` (write)
- `x` (execute)

### Tools Used
- `chmod` – Modifies permission bits
- `chown` – Changes file owner and group
- `ls -l` – Displays file permission settings

### 📎 Example
```bash
chmod 755 myscript.sh
chown lucy: developers myscript.sh
```
These commands give full permissions to the owner, and read-execute to the group and others.

---

## 2. File Attributes: `setuid`, `setgid`, and Sticky Bit

These are special permission bits that enhance access control for executable files and shared directories.

###  `setuid`  
Runs a file with the permissions of its file owner (commonly used with system binaries).

```bash
chmod u+s /usr/bin/example
```

###  `setgid`  
Ensures files created in a directory inherit the directory’s group.

```bash
chmod g+s /var/dev_shared
```

###  Sticky Bit  
Prevents users from deleting other users’ files in shared directories (e.g., `/tmp`).

```bash
chmod +t /var/dev_shared
```

---

## 3. Access Control Lists (ACLs)

ACLs allow more granular access management beyond the standard three-user model.

### Tools Used
- `setfacl` – Sets ACL permissions
- `getfacl` – Views ACL settings

###  Example
```bash
setfacl -m u:bob:rw confidential.txt
getfacl confidential.txt
```
This gives user `bob` read and write access to `confidential.txt` without changing its ownership.

---

## Conclusion

Linux provides multiple layers of access control. From basic file permissions to special attributes and ACLs, these tools allow system administrators to enforce security and proper user isolation in multi-user environments. Mastery of these controls is crucial for any Linux security practitioner.

---

## Author

**Lucy Njuguna**  
Cybersecurity Professional | Linux Security Enthusiast
