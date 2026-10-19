# Linux Terminologies 

**Kernel :** Glue between hardware and applications

**Distribution :** Collection of software making up a Linux-Based OS 

**Boot Loader :** Program that boots the OS (Eg:- GRUB) 

**Filesystem :** Method for storing and organizing files in Linux 

**X Window System(X11/X) :** Graphical subsystem on nearly all Linux systems; provides the basic framework for GUIs, including drawing and moving windows, handling keyboard and mouse input, and supporting multiple screens and displays.

**Command-Line :** Interface for typing commands

---
**Note:- Shell and Terminal are not the same.**                                                                                                                     
                                                                                                                                                                  
- Terminal(The Window) - The visual window or program on ur screen where u type; captures your keystrokes and displays the text.                                      
                                                                                                                                                                    
- Shell(The Interpreter) - Underlying program running inside the terminal. It reads the commands you type, translates them for the OS kernel and executes them. 

- Command Line(The Interface) - The actual text-mode interface where the cursor blinks, waiting for u to type a command.


## The Linux Boot Process

The boot process is the sequence of steps a computer follows
from power-on until the operating system is ready to use.

### 1. Power ON

- The computer receives power.
- The CPU begins executing firmware instructions.
- The system starts its initialization process.

### 2. BIOS/UEFI

- BIOS stands for Basic Input/Output System.
- UEFI stands for Unified Extensible Firmware Interface.
- Firmware initializes essential hardware and begins the boot process.
- Firmware is stored in non-volatile memory on the motherboard.
- Modern PCs generally use UEFI, while older systems commonly use BIOS.

### 3. POST

- POST stands for Power-On Self-Test.
- It checks and initializes essential hardware during startup.
- Hardware problems may prevent the system from booting normally.

### 4. MBR (Master Boot Record)

- Used in the traditional BIOS boot process.
- Located in the first sector of a partitioned disk.
- Contains initial boot code, a partition table, and a boot signature.
- The traditional MBR sector is 512 bytes.
- Its initial boot code helps begin the next boot stage.

### 5. Bootloader (GRUB)

- GRUB stands for GNU GRand Unified Bootloader.
- It is commonly used by Linux distributions such as Ubuntu.
- It can display a boot menu and select a Linux kernel.
- It loads the kernel and, when configured, the initramfs.
- GRUB can be used with both BIOS and UEFI systems.

### 6. Linux Kernel

- The bootloader loads the kernel into memory and transfers control to it.
- The kernel initializes essential hardware and system components.
- It sets up memory management, process management, and device drivers.

### 7. Initramfs and Root Filesystem

- **Initramfs:** A temporary filesystem loaded into RAM during boot. It contains essential programs, device drivers, and tools needed to access and mount the actual root filesystem.
- **Device Detection:** Tools such as `udev` help identify devices and manage device nodes; required drivers may be loaded to enable hardware access.
- **Root Filesystem:** Once located, it is checked and mounted at the appropriate mount point in the filesystem hierarchy.
- **Switching to the Real Root:** The boot process switches from initramfs to the actual root filesystem, and the system's init process (usually `systemd` on Ubuntu) starts.
- **Important:** Drivers required to access the storage containing the root filesystem must be available during early boot, including in the initramfs when necessary.

### 8. Init System and Services

- The kernel starts the first user-space process.
- Ubuntu commonly uses systemd as its system and service manager.
- The system starts necessary services and prepares the operating environment.
- The login screen eventually becomes available.

### Boot Sequence: Traditional BIOS System

Power ON
    ↓
BIOS
    ↓
POST
    ↓
Bootable device and initial boot code
    ↓
GRUB bootloader
    ↓
Linux kernel
    ↓
Initramfs (if used)
    ↓
Root filesystem
    ↓
Init system (systemd on Ubuntu)
    ↓
Services and login screen

Note: This is a simplified BIOS boot sequence.
UEFI systems use a different firmware boot mechanism and
commonly launch a bootloader from the EFI System Partition.

### Key Takeaways

- BIOS/UEFI performs the initial firmware startup.
- POST checks essential hardware during startup.
- MBR is associated with traditional BIOS booting.
- GRUB helps load the Linux kernel.
- The kernel initializes the operating system.
- Initramfs helps prepare access to the root filesystem.
- systemd starts and manages system services on Ubuntu.

