# 🌐 Networking & Security

This module covers Linux networking fundamentals, network interface configurations via Netplan, traffic diagnostic tools, and SSH service hardening.

---

## 📚 Module Curriculum

- [x] **Network Diagnostics & Management** (`ip`, `ss`, `netstat`, `ping`, `traceroute`, `dig`, `nmcli`)
- [x] **Topology Setup & Static Configuration** (`/etc/netplan/`, Netplan YAML configs, Gateway & DNS)
- [ ] **SSH Server Management & Hardening** (`sshd_config`, Key Authentication, Port Forwarding, UFW/iptables)

---

## 📌 Network Diagnostics & Utilities

Tools for inspecting network interfaces, active sockets, routing tables, and connectivity.

| Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `ip addr` | Displays or configures network interface addresses | `ip addr show eth0` |
| `ip route` | Displays or modifies the kernel IP routing table | `ip route show` |
| `ss` | Utility to investigate network sockets (modern replacement for `netstat`) | `ss -tulpn` |
| `ping` | Sends ICMP ECHO_REQUEST packets to network hosts | `ping -c 4 8.8.8.8` |
| `traceroute` | Tracks the route packets take to a network host | `traceroute google.com` |
| `dig` / `nslookup` | DNS lookup utilities for querying name servers | `dig +short example.com` |

---

## 📌 Network Configuration (Netplan)

Modern network configuration abstraction tool used in Ubuntu/Debian systems.

| Configuration / Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `/etc/netplan/*.yaml` | Netplan configuration files location | `sudo nano /etc/netplan/01-netcfg.yaml` |
| `netplan try` | Tests configuration changes with automatic rollback safety | `sudo netplan try` |
| `netplan apply` | Applies new network configuration settings immediately | `sudo netplan apply` |

### Key Netplan Example (Static IP)
```yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    eth0:
      addresses:
        - 192.168.1.100/24
      routes:
        - to: default
          via: 192.168.1.1
      nameservers:
        addresses: [1.1.1.1, 8.8.8.8]
