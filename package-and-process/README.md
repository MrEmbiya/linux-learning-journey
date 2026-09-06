# ⚙️ Package, Process & Service Management

This module covers package manager operations, process execution and signals, init systems (`systemd`), and automated cron scheduling.

---

## 📚 Module Curriculum

- [x] **Package & Repository Management** (`apt`, `dpkg`, `flatpak`, `/etc/apt/sources.list`)
- [x] **Installation & Execution Control** (`make`, `./configure`, binary execution paths)
- [x] **Process Management** (`ps`, `top`, `htop`, `kill`, `nice`, `renice`)
- [x] **Services & Init Systems** (`systemctl`, `journalctl`, `.service` files)
- [x] **Task Scheduling & Automation** (`crontab`, `/etc/crontab`)

---

## 📌 Package & Repository Management

Handling software installation, system updates, and repository sources.

| Utility / File | Description | Syntax Example |
| :--- | :--- | :--- |
| `apt` | High-level package management tool (Debian/Ubuntu) | `sudo apt update && sudo apt upgrade -y` |
| `dpkg` | Low-level Debian package tool | `sudo dpkg -i package.deb` |
| `flatpak` | Universal sandboxed application deployment tool | `flatpak install flathub org.videolan.VLC` |
| `/etc/apt/sources.list` | Defines repository mirror sources | `cat /etc/apt/sources.list` |

---

## 📌 Process Management

Monitoring system processes, CPU/Memory resource consumption, and signals.

| Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `ps aux` | Displays a static snapshot of current running processes | `ps aux \| grep nginx` |
| `top` / `htop` | Dynamic real-time process monitoring interface | `htop` |
| `kill` / `killall` | Sends signals (SIGTERM/SIGKILL) to terminate processes | `kill -9 <PID>` |
| `bg` / `fg` | Manages background and foreground job states | `bg %1` |

---

## 📌 Services & Systemd

Managing background daemons, system targets, and logging services.

| Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `systemctl start/stop` | Starts or stops a system service immediately | `sudo systemctl stop nginx` |
| `systemctl enable` | Configures a service to start automatically on boot | `sudo systemctl enable nginx` |
| `systemctl status` | Shows detailed operational status and recent logs of a service | `systemctl status sshd` |
| `journalctl` | Interrogates systemd log journal | `journalctl -u nginx -f --since "1 hour ago"` |

---

## 📌 Task Automation (Cron)

Automating recurring scripts and system maintenance.

| Command / Path | Description | Syntax Example |
| :--- | :--- | :--- |
| `crontab -e` | Opens the current user's cron schedule for editing | `crontab -e` |
| `crontab -l` | Lists active scheduled cron tasks | `crontab -l` |

### Key Syntax
`* * * * * /path/to/command` -> `[Min] [Hour] [DayOfMonth] [Month] [DayOfWeek]`
* **Example:** `0 3 * * 1 /scripts/backup.sh` (Runs every Monday at 03:00 AM).
