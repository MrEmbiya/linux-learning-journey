# 🚀 Server Infrastructure & Labs

This module covers core enterprise server services (DHCP, DNS, Web, Directory Services, File Sharing) and multi-distro hands-on lab deployments (Ubuntu Server & CentOS).

---

## 📚 Module Curriculum

- [x] **Multi-Distro Server Administration** (Fedora, Ubuntu Server & CentOS/Rocky Linux)
- [x] **Headless Management & CLI Administration** (Remote console, serial, TUI interfaces)
- [x] **DHCP Server Management** (ISC-DHCP / Kea DHCP configuration, leases, pools)
- [ ] **DNS Server Management** (BIND9, Forward/Reverse lookup zones, resolution)
- [ ] **Web Server Administration** (Nginx & Apache HTTP Server setup, virtual hosts, SSL)
- [ ] **Domain Controller & Directory Services** (Samba DC, Active Directory integration)
- [ ] **File Server Management** (NFS exports, Samba/CIFS network shares)
- [ ] **Hands-on Integration Labs** (Ubuntu Server & CentOS Server Lab deployments)

---

## 📌 Core Network Services

Server roles providing fundamental infrastructure services to client nodes.

| Service Role | Key Software / Tools | Primary Config / Command |
| :--- | :--- | :--- |
| **DHCP Server** | `isc-dhcp-server` / `kea` | `/etc/dhcp/dhcpd.conf` |
| **DNS Server** | `bind9` / `named` | `/etc/bind/named.conf.local` |
| **Web Server** | `nginx` / `apache2` | `/etc/nginx/sites-available/` |
| **File Sharing (Linux)** | `nfs-kernel-server` | `/etc/exports` |
| **File Sharing (Cross-Platform)**| `samba` | `/etc/samba/smb.conf` |
| **Directory Services** | `samba-ad-dc` / `freeipa` | `samba-tool domain provision` |

---

## 📌 Web Server Administration (Nginx / Apache)

Deploying and serving web applications securely.

| Task | Nginx | Apache |
| :--- | :--- | :--- |
| **Service Name** | `nginx` | `apache2` or `httpd` |
| **Virtual Host Location** | `/etc/nginx/sites-available/` | `/etc/apache2/sites-available/` |
| **Config Test Command** | `sudo nginx -t` | `sudo apachectl configtest` |
| **Default Document Root** | `/var/www/html` | `/var/www/html` |

---

## 📌 Hands-On Server Labs

Integrated lab scenarios built to simulate production enterprise network topologies.

| Lab Scenario | Primary Focus | Target Operating System |
| :--- | :--- | :--- |
| **Ubuntu Server Lab** | Web services, Netplan routing, Systemd services | Ubuntu Server 22.04 / 24.04 LTS |
| **CentOS / Rocky Lab** | Enterprise storage, SELinux policies, FirewallD | CentOS Stream / Rocky Linux 9 |
| **File & Domain Lab** | Samba Active Directory Integration & NFS Shares | Multi-node Linux Environment |
