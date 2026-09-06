# 💾 Storage & Disk Management

This module covers physical disk partitioning, filesystem creation, mount tables, and Logical Volume Management (LVM).

---

## 📚 Module Curriculum

- [x] **Disk Inspection & Partitioning** (`lsblk`, `fdisk`, `parted`)
- [x] **Filesystem Formatting & Management** (`mkfs`, `ext4`, `xfs`)
- [x] **Mounting & Auto-Mount Configurations** (`mount`, `umount`, `/etc/fstab`)
- [x] **Logical Volume Management (LVM)** (`pvcreate`, `vgcreate`, `lvcreate`)

---

## 📌 Disk Inspection & Partitioning

Identifying block devices, partitioning schemas (MBR/GPT), and disk structures.

| Command | Description | Syntax Example |
| :--- | :--- | :--- |
| `lsblk` | Lists block devices in a tree-like hierarchy | `lsblk -f` |
| `df -h` | Displays filesystem disk space usage in human-readable format | `df -h` |
| `fdisk` | Manipulates disk partition tables (MBR/GPT) | `sudo fdisk /dev/sdb` |
| `parted` | Advanced partition manipulation tool for large disks | `sudo parted /dev/sdb` |

---

## 📌 Filesystem Formatting & Mounting

Creating filesystems and mounting storage devices into the system tree.

| Utility / File | Description | Syntax Example |
| :--- | :--- | :--- |
| `mkfs.ext4` | Formats a partition with the Ext4 filesystem | `sudo mkfs.ext4 /dev/sdb1` |
| `mount` | Mounts a device to a specific directory target | `sudo mount /dev/sdb1 /mnt/data` |
| `umount` | Unmounts a mounted filesystem | `sudo umount /mnt/data` |
| `/etc/fstab` | File defining persistent automatic mounts at boot time | `UUID=xxx /mnt/data ext4 defaults 0 2` |

---

## 📌 Logical Volume Management (LVM)

Abstracting physical storage for flexible volume resizing and management.

| LVM Layer | Command | Description | Syntax Example |
| :--- | :--- | :--- | :--- |
| **Physical Volume (PV)** | `pvcreate` | Initializes raw disks/partitions for LVM use | `sudo pvcreate /dev/sdb1` |
| **Volume Group (VG)** | `vgcreate` | Combines PVs into a single storage pool | `sudo vgcreate vg_data /dev/sdb1` |
| **Logical Volume (LV)** | `lvcreate` | Allocates virtual partitions from the VG pool | `sudo lvcreate -L 10G -n lv_app vg_data` |
| **LV Resize** | `lvextend` | Expands logical volume capacity dynamically | `sudo lvextend -L +5G -r /dev/vg_data/lv_app` |
