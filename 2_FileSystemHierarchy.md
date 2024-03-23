- To view tree structure use:
```
apt install tree -y
tree -L 1 /
```

  


| Directory | Purpose |
|-----------|---------|
| `/`       | The root directory is the top-level of the file system hierarchy. Everything on the system is under this directory. |
| `/bin`    | Contains essential user binaries (programs) like ls, cp, and mv that are necessary for the user and system operations. |
| `/boot`   | Holds files required for system boot-up, including the Linux kernel, initrd, and bootloader configuration files like GRUB. |
| `/dev`    | Contains device files that represent hardware components or other system devices, allowing the system and users to interact with them. |
| `/etc`    | Houses configuration files that are local to the machine. System-wide application settings are typically found here. |
| `/home`   | The directory where user home directories are located. Each user is given a directory within `/home` for personal storage. |
| `/lib`    | Contains essential shared libraries and kernel modules that are needed for the binaries in `/bin` and `/sbin` to function. |
| `/media`  | A mount point for removable media such as USB drives, CD-ROMs, etc. Modern systems may use `/run/media` instead. |
| `/mnt`    | A temporary mount point where system administrators can mount filesystems manually. |
| `/opt`    | Intended for the installation of add-on application software packages. |
| `/proc`   | A virtual filesystem that provides process and kernel information as files. In essence, it does not contain 'real' files but runtime system information. |
| `/root`   | The home directory for the root user (system administrator). It is not under `/home` to ensure the root user retains access even if `/home` is unmounted. |
| `/run`    | A temporary filesystem that stores volatile runtime data, reflecting the system's state since the last boot, including currently running processes. |
| `/sbin`   | Holds essential system binaries, like system and service management utilities, that are usually required by the system administrator. |
| `/srv`    | Contains data for services provided by the system. |
| `/sys`    | Provides a lot of detailed information about the system's hardware and is used for kernel interaction with the hardware. |
| `/tmp`    | A temporary directory where programs and users can store temporary files. Often cleared on reboot or through a scheduled job. |
| `/usr`    | Considered the secondary hierarchy for read-only user data; contains the majority of (multi-)user utilities and applications, libraries, documentation, etc. |
| `/var`    | Contains variable data files such as logs, databases, websites, and temporary e-mail files, whose content is expected to continually change during normal operation of the system. |
| `/var/log`| Contains system log files that are important for analyzing and troubleshooting. Logs of various system activities and applications are kept here. |
