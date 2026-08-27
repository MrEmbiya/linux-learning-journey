# 🐧 Linux Learning Journey

> A structured, production-ready repository documenting my personal Linux learning progress, command-line practices, system administration notes, and hands-on labs.

---

## 📖 About

This repository serves as my primary public notebook for Linux systems engineering and administration. 

Instead of getting bogged down in theoretical overload, this journey focuses on **Just-In-Time Learning**—understanding core OS principles, command-line usage, network infrastructure, and server management through hands-on practice.

> All notes, command references, and lab results are updated continuously as I progress through each topic.

---

## 📚 Curriculum & Roadmap

- [x] **01-commands-and-shell**
  - [x] Commands & Shell Basics
  - [x] Shell Interpreters & Management
  - [x] Customization & Environment Settings (`.bashrc`, `alias`, `export`)

- [ ] **02-system-administration**
  - [x] User & Group Management
  - [x] SUDO Management
  - [x] Object Permissions & Access Control (`chmod`, `chown`, `umask`)
  - [ ] Symlink & Hardlink Management (`ln`, `inodes`)

- [ ] **03-package-and-process**
  - [ ] Package, Repository & Update Management (`apt`, `dpkg`, `flatpak`)
  - [ ] Installation & Execution Control
  - [ ] Process Management (`ps`, `top`, `htop`, `kill`)
  - [ ] Runlevels & Services (`systemctl`, `systemd`)
  - [ ] Task Scheduling & Automation (`cron`, `crontab`)

- [ ] **04-storage-and-disks**
  - [ ] Disk & File System Management (Partitioning, Formatting, Mounting)
  - [ ] Logical Volume Management (LVM & `/etc/fstab`)

- [ ] **05-networking-and-security**
  - [ ] Network Management & Tools (`ip`, `ss`, `netstat`)
  - [ ] Topology Changes & Network Setup (Netplan, Static IP)
  - [ ] SSH Server & Key Management (Hardening & Config)

- [ ] **06-server-infrastructure-and-labs**
  - [ ] Multi-Distro Server Administration (Fedora, Ubuntu & CentOS)
  - [ ] Headless Server Management
  - [ ] DHCP Server & Management
  - [ ] DNS Server & Management
  - [ ] Web Server Administration (Nginx / Apache)
  - [ ] Domain Controller (DC) Server Management
  - [ ] File Server Management (NFS / Samba)
  - [ ] Lab Setups (Ubuntu Server & CentOS Integration)
  - [ ] Advanced System Administration & Troubleshooting

---

## 📂 Repository Structure

```text
linux-learning-journey/
│
├── README.md                          # Main overview and curriculum roadmap
│
├── 01-commands-and-shell/             # CLI navigation, shell interpreters, aliases & environment
├── 02-system-administration/          # Users, groups, sudo, permissions & file links (symlinks)
├── 03-package-and-process/            # Package managers (apt), process control, systemd & cron
├── 04-storage-and-disks/              # Disk partitioning, filesystems, mount & LVM
├── 05-networking-and-security/         # Network configuration (Netplan), routing, SSH security
└── 06-server-infrastructure-and-labs/ # Server services (Web/DNS/DHCP/DC/File) & Lab deployments
