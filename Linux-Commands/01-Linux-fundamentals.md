## Linux Kernel and Distributions

# 1. What is Linux?
The kernel is the central component of a Linux-based operating system. It manages hardware resources and provides essential services to software.
Think of the kernel as the manager of a computer's resources. (Example of Kernel is a Linux Kernal)

Its responsibilities include:
- Process management.
- Memory management.
- Device management.
- File-system operations.
- Networking.
- System-call handling.
  
# 2. What is a Linux distribution?
Different organizations and communities combine the kernel with different collections of software to create complete operating systems.
A collection of software built around the Linux kernel is called a Linux distribution or Linux distro.

A distribution includes:
- Linux kernel.
- System utilities.
- Libraries.
- Package manager.
- Software repositories.
- Applications.
- Configuration tools.
  
Different distributions have different design goals, software choices, and maintenance policies. 
So keep in mind that different distributions are designed to meet different needs.

# 3. Major Linux distribution families
Debian-based distributions
- Debian
- Ubuntu
- Linux Mint
--> Ubuntu is based on Debian, and the main edition of Linux Mint is based on Ubuntu.

Red Hat and related enterprise Linux ecosystem
- Fedora
- Red Hat Enterprise Linux (RHEL)
- CentOS Stream
- Oracle Linux
--> These distributions are related through the broader Red Hat and enterprise Linux ecosystem, but they have different roles and their relationships differ.

SUSE ecosystem
- SUSE Linux Enterprise Server (SLES) (focuses on enterprise use)
- openSUSE (provides community Linux distributions with different release models)
--> SLES is an enterprise distribution. openSUSE includes community distributions such as Leap and Tumbleweed.

Other distributions
- Arch Linux
- Gentoo Linux
- Alpine Linux
--> These have their own package management tools.

4. Package management
Package managers install, update, and remove software.
Distribution	Common package manager
Ubuntu - APT(Advanced Package Tool; uses .deb packages)
Debia - APT
Fedora - DNF(Debian Package Manager; uses RPM packages)
RHEL - DNF
Oracle Linux - 	DNF
openSUSE- Zypper(uses RPM packages)
Arch Linux - Pacman(uses .packman packages)
--> These package managers are essential for managing software on Linux distributions, ensuring system stability and security.
--> Ubuntu uses DEB packages, while Fedora and many RHEL-family distributions use RPM packages.

Linux Terminologies :
Kernel :- Glue between hardware and applications
Distribution :- Collection of software making up a Linux-Based OS
Boot Loader :- Program that boots the OS (Eg:- GRUB)
Filesystem :- Method for storing and organizing files in Linux 
X Window System(X11/X) - Graphical subsystem on nearly all Linux systems; provides the basic framework for GUIs, including drawing and moving windows, handling keyboard and mouse input, and supporting multiple screens and displays.
Command-Line :- Interface for typing commands
___________________________________________________________________________________________________________________________________________________________________
 # Note:- Shell and Terminal are not the same. 
   Terminal(The Window) - The visual window or program on ur screen where u type; captures your keystrokes and displays the text.
   Shell(The Interpreter) - Underlying program running inside the terminal. It reads the commands you type, translates them for the OS kernel and executes them.
   Command Line(The Interface) - The actual text-mode interface where the cursor blinks, waiting for u to type a command.
___________________________________________________________________________________________________________________________________________________________________


Commands:- 
1) man <topic> --> command to open a built-in user manual in Linux systems.
   
6. Commands to identify my system
Check distribution information
cat /etc/os-release

Displays the installed distribution's identification and release information.
Check kernel version
uname -r

Displays the release version of the running kernel.
Check machine architecture
uname -m

