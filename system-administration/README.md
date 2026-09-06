# 👤 System Administration & Security

This module covers Linux user and group management, privilege escalation with SUDO, standard and special permission controls, and file link mechanics.

---

## 📚 Module Curriculum

- [x] **User & Group Management** (`useradd`, `usermod`, `groupadd`, `/etc/passwd`, `/etc/shadow`)
- [x] **SUDO Management** (`sudo`, `visudo`, `/etc/sudoers`)
- [x] **Object Permissions & Access Control** (`chmod`, `chown`, `chgrp`, `umask`)
- [x] **Special Permissions** (`SUID`, `SGID`, `Sticky Bit`)
- [x] **Symlink & Hardlink Management** (`ln`, `ln -s`, `inodes`)

---

## 📌 User & Group Management

Commands and critical files for managing user identities and system access.

| Command / File | Description | Syntax Example |
| :--- | :--- | :--- |
| `useradd` | Creates a new user account | `sudo useradd -m -s /bin/bash sysadmin` |
| `usermod` | Modifies an existing user account attributes | `sudo usermod -aG sudo sysadmin` |
| `userdel` | Deletes a user account and optionally home directory | `sudo userdel -r olduser` |
| `groupadd` | Creates a new user group | `sudo groupadd devops` |
| `/etc/passwd` | Stores user account parameters (UID, GID, home, shell) | `cat /etc/passwd` |
| `/etc/shadow` | Stores encrypted password hashes and expiration data | `sudo cat /etc/shadow` |

---

## 📌 Privilege Escalation (SUDO)

Configuring root privileges and access security policies.

| Utility / File | Description | Syntax Example |
| :--- | :--- | :--- |
| `sudo` | Executes a command with elevated root permissions | `sudo apt update` |
| `visudo` | Safely edits the `/etc/sudoers` file with syntax validation | `sudo visudo` |
| `/etc/sudoers` | Configuration file determining user privilege rules | `username ALL=(ALL:ALL) ALL` |

---

## 📌 Permissions & Access Control

Managing file modes, ownerships, and default creation masks.

| Command / Term | Description | Syntax Example |
| :--- | :--- | :--- |
| `chmod` | Changes access permissions for owner, group, and others | `chmod 755 script.sh` |
| `chown` | Changes file ownership (user and/or group) | `sudo chown -R devops:devops /var/www` |
| `umask` | Determines default permissions for new files/directories | `umask 022` |

### Key Notes (Permissions & Special Bits)
* **Numeric Values:** Read (`4`), Write (`2`), Execute (`1`).
* **SUID (4000):** Runs file with owner's privilege (`chmod u+s file`).
* **SGID (2000):** New files in directory inherit group ownership (`chmod g+s dir`).
* **Sticky Bit (1000):** Only file owners can delete files in shared folder (`chmod +t /tmp`).

---

## 📌 Link Management

Concepts for linking filesystem resources to inodes.

| Concept | Description | Syntax Example |
| :--- | :--- | :--- |
| **Hard Link** | Point directly to the exact file inode (same filesystem) | `ln original.txt hardlink.txt` |
| **Symbolic Link** | Creates a shortcut pointing to target file path | `ln -s /etc/nginx/sites-avail/app /etc/nginx/sites-enabled/` |
