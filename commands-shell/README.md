# 🐚 Commands & Shell Basics

This module covers fundamental terminal navigation, help documentation utilities, system inspection, file operations, content viewing, archiving, shell operators, and shell environment customization.

---

## 📚 Module Curriculum

- [x] **Help Commands** (`man`, `help`, `--help`, `whatis`, `info`)
- [x] **System Information Commands** (`uname`, `hostname`, `uptime`, `whoami`)
- [x] **Content Viewing Commands** (`cat`, `head`, `tail`, `less`, `more`)
- [x] **File & Directory Commands** (`mkdir`, `rm`, `cp`, `mv`, `touch`)
- [x] **Archiving Commands** (`tar`, `gzip`, `zip`, `unzip`)
- [x] **Command Operators** (`&&`, `||`, `;`, `|`, `>`, `>>`)
- [x] **Shell Interpreters & Management** (`/etc/shells`, `chsh`, `zsh`)
- [x] **Configuration Profiles & Reloading** (`.bashrc`, `.bash_profile`, `source`)
- [x] **Shell History Management** (`history`, `!n`, `Ctrl+R`)
- [x] **Aliases & Custom Shortcuts** (`alias`, `unalias`)
- [x] **Environment Variables & PATH** (`export`, `env`, `printenv`, `$PATH`)

---

## 📌 Help Commands

Methods for accessing documentation and command manuals directly within the terminal.

| Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `man` | Displays the manual page for a command | `man ls` |
| `help` | Shows help for shell built-in commands | `help cd` |
| `--help` | Shows brief usage instructions for CLI tools | `ls --help` |
| `whatis` | Displays a single-line manual description | `whatis pwd` |
| `info` | Displays detailed, hyperlinked documentation | `info coreutils` |

### Key Notes
* Press `q` to exit `man` or `info` page views.
* Use `/keyword` inside `man` to search for specific options (press `n` for next match).

---

## 📌 System Information Commands

Tools to inspect operating system properties, uptime, and identity.

| Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `uname` | Prints system information (Kernel, OS architecture) | `uname -a` |
| `hostname` | Displays or sets the system's network name | `hostname -I` |
| `uptime` | Shows how long the system has been running + load average | `uptime` |
| `whoami` | Prints the current effective username | `whoami` |

---

## 📌 Content Viewing Commands

Commands used to inspect, output, and paginate file contents.

| Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `cat` | Concatenates and prints entire file contents | `cat /etc/os-release` |
| `head` | Outputs the first part of files (Default: first 10 lines) | `head -n 20 /var/log/syslog` |
| `tail` | Outputs the last part of files (Default: last 10 lines) | `tail -n 15 /var/log/syslog` |
| `less` | Page-at-a-time view allowing forward/backward navigation | `less /var/log/auth.log` |
| `more` | Basic file viewing filter for page-by-page viewing | `more /etc/services` |

### Key Notes
* Use **`tail -f /var/log/syslog`** to stream live log updates in real-time (essential for troubleshooting).
* In `less`, navigate using `PageUp`/`PageDown` or `j`/`k` keys, and search with `/pattern`.

---

## 📌 File & Directory Management

Commands for creating, copying, moving, and removing files or directories.

| Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `mkdir` | Creates new directories | `mkdir -p project/src/bin` |
| `touch` | Creates empty files or updates existing timestamps | `touch index.html` |
| `cp` | Copies files or directories | `cp -r src/ dist/` |
| `mv` | Moves or renames files and directories | `mv old_name.txt new_name.txt` |
| `rm` | Removes files or directories | `rm -rf temp_dir/` |

---

## 📌 Archiving & Compression

Utilities to bundle multiple files and compress archive sizes.

| Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `tar` | Archives files into a single `.tar` or `.tar.gz` bundle | `tar -czvf backup.tar.gz /var/www` |
| `gzip` | Compresses or decompresses single files (`.gz`) | `gzip -d file.txt.gz` |
| `zip` | Creates compressed `.zip` archives | `zip -r logs.zip /var/log` |
| `unzip` | Extracts files from a `.zip` archive | `unzip logs.zip -d ./extracted` |

### Key Flags for `tar`
* `-c` : Create a new archive.
* `-z` : Compress using `gzip`.
* `-v` : Verbose mode (list files processed).
* `-f` : Specify the archive file name.
* `-x` : Extract an archive.

---

## 📌 Command Operators & Redirection

Control execution flow and redirect standard input/output streams.

| Operator | Function | Example |
| :--- | :--- | :--- |
| `>` | Redirects output to a file (Overwrites) | `echo "hello" > file.txt` |
| `>>` | Appends output to the end of a file | `echo "world" >> file.txt` |
| `\|` | Pipes stdout of one command as stdin to another | `cat /etc/passwd \| grep sudo` |
| `&&` | Logical AND: Runs 2nd command **only if** 1st succeeds | `mkdir build && cd build` |
| `\|\|` | Logical OR: Runs 2nd command **only if** 1st fails | `cd project \|\| mkdir project` |
| `;` | Command separator: Runs commands sequentially | `clear; ls -la; pwd` |

---

## 📌 Shell Customization & Environment Management

Utilities and concepts for configuring shell environments, managing environment variables, shortcuts, and history.

| Concept / Command | Description | Syntax Example |
| :--- | :--- | :--- |
| **Shell Listing & Change** | Displays active shells and changes current shell (`chsh`) | `cat /etc/shells` / `chsh -s /bin/zsh` |
| **Shell History** | Displays, searches, or manages command history | `history` / `!42` / `history -c` |
| `alias` | Defines custom command shortcuts | `alias ll='ls -la'` |
| `unalias` | Removes a defined alias | `unalias ll` |
| `export` | Sets or exports environment variables to subshells | `export EDITOR=vim` |
| `env` / `printenv` | Lists all active environment variables | `printenv PATH` |
| `source` | Executes commands from a file in the current shell context | `source ~/.bashrc` |

### Key Notes & Files
* **Shell Startup Files:** 
  * `~/.bashrc` : Executes for interactive non-login shells (ideal for aliases, custom functions, and `PATH` exports).
  * `~/.bash_profile` / `~/.profile` : Executes for interactive login shells.
* **Working with PATH:** Adding a custom binary path: `export PATH=$PATH:/custom/path/bin`.
* **History Shortcuts:**
  * `Ctrl + R` : Reverse search through command history.
  * `!!` : Re-runs the last executed command.
  * `!$` : Reuses the last argument of the previous command.
