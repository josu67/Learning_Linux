# Linux Boot Process and Filesystems

## 1. Linux Boot Process

The boot process is the sequence of steps a computer follows to start the operating system.

### Steps involved

1. **Power ON:** The computer receives power and begins starting up.

2. **BIOS/UEFI:** Firmware initializes the hardware and performs POST (Power-On Self-Test) to check essential components.

3. **Bootloader:** BIOS/UEFI identifies a bootable device and starts its bootloader. GRUB is a common Linux bootloader.

4. **Kernel:** The bootloader loads the Linux kernel into memory and transfers control to it. The kernel initializes hardware and essential system components.

5. **Initramfs:** A temporary filesystem in memory that provides tools and drivers needed to locate and mount the actual root filesystem.

6. **Init System (systemd):** The kernel starts the initial userspace process, usually systemd on modern Ubuntu systems. It starts and manages system services.

7. **Login Screen/Desktop:** The system becomes ready for the user to log in and use applications.

**Boot sequence:**
Power ON → BIOS/UEFI → Bootloader (GRUB) → Kernel → Initramfs → Root Filesystem → systemd → Login Screen/Desktop

---

## 2. Init System and systemd

- **Init system:** The first userspace process started by the kernel. It manages system startup.
- **systemd:** The init system used by Ubuntu that starts and manages services, handles dependencies, and supports system shutdown.
- **Services/Daemons:** Background programs that perform tasks such as networking, logging, and web hosting.
- **PID 1:** The process ID usually assigned to the init system.

---

## 3. Linux Filesystem Basics

A filesystem defines how data is stored, organized, and accessed on a storage device.

Examples:
- ext4 — Common Linux filesystem.
- XFS — Filesystem commonly used on servers.
- FAT32/exFAT — Commonly used on removable storage.
- NTFS — Commonly used by Windows.

Linux supports conventional, flash-storage, network, virtual, and special-purpose filesystems.

---

## 4. Partitions vs. Filesystems

- **Partition:** A logical division of a storage device.
- **Filesystem:** The structure used to organize files and directories within storage.
- A partition can contain a filesystem, but not every partition must contain one.
- A filesystem can also span multiple devices or partitions.

**Example:** A disk can have separate partitions for the operating system and personal data.

---

## 5. Linux Directory Structure

Linux organizes files in a single directory hierarchy beginning at `/`, called the root directory.

Unlike Windows, Linux does not normally organize files using separate drive letters such as `C:` and `D:`. Storage devices are accessed through mount points within the directory hierarchy.

### Important directories

| Directory | Purpose |
|---|---|
| `/` | Root of the entire filesystem hierarchy |
| `/home` | Personal directories of regular users |
| `/root` | Home directory of the root user |
| `/etc` | System configuration files |
| `/bin` | Essential user commands; commonly linked to `/usr/bin` on modern Ubuntu |
| `/usr` | Most user-space applications, libraries, and supporting files |
| `/var` | Frequently changing data, such as logs |
| `/tmp` | Temporary files |
| `/dev` | Device files |
| `/boot` | Files needed for booting, including the kernel and bootloader-related files |
| `/mnt` | Commonly used as a temporary mount point |
| `/media` | Common mount point for removable media |

---

## 6. Filesystem Hierarchy Standard (FHS)

The Filesystem Hierarchy Standard (FHS) describes the conventional organization and purpose of directories in Linux.

It helps maintain consistency across Linux distributions, making system files, configuration files, applications, and variable data easier to locate.

---

## 7. Symbolic Links

A symbolic link (symlink) is a special file that points to another file or directory.

It acts like a shortcut, allowing the same destination to be accessed through another path.

---

## Key Takeaways

- The boot process takes Linux from power-on to a usable system.
- GRUB loads the kernel; the kernel initializes the system.
- Initramfs helps the kernel locate and mount the root filesystem.
- systemd manages userspace startup and system services.
- A partition is a storage division; a filesystem organizes data.
- Linux uses one unified directory hierarchy starting at `/`.
- FHS defines the conventional purposes of Linux directories.
