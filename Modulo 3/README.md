🌐 [English](README.md) | [Spanish](README.es.md) | [Go back](https://github.com/martinmorente-dev/Cisco-Cyberops/tree/main)

# Windows History

## Vulnerabilities in the SO

A vulnerability is an imperfection or weakness that it could be used by an attacker to reduce the viability of information. To take advantage over a system vulnerability, the attacker need to use a technique or tool to attack it. The attacker can use a vulnerability for the computer to act in a different way that isn't design for.

The next table show some common security recommendations of the windows SO.

| Recommendation | Description |
|---|---|
| Virus or malware protection | • By default, Windows uses Windows Defender for malware protection.<br>• Windows Defender provides a set of protection tools built into the system.<br>• If Windows Defender is disabled, the system is more vulnerable to attacks and malware. |
| Unknown or unmanaged services | • Many services run in the background.<br>• It is important to make sure that every service can be identified and is safe.<br>• With an unknown service running in the background, the computer may be vulnerable to attacks. |
| Encryption | • When data is not encrypted, it can easily be collected and exploited.<br>• This is important not only for desktop computers, but especially for mobile devices. |
| Security policy | • A good security policy must be configured and enforced.<br>• Many settings in the Windows security policy controls can prevent attacks. |
| Firewall | • By default, Windows uses Windows Firewall to limit communication with devices on the network.<br>• Over time, rules may no longer apply.<br>• For example, a port that should no longer be available could be left open.<br>• It is important to review the firewall configuration periodically to make sure the rules are still applicable, and to remove those that no longer apply. |
| File permissions and sharing | • These permissions must be applied correctly.<br>• It is easy to simply give the "Everyone" group full control, but this allows anyone to do whatever they want with all files.<br>• It is better to grant each user or group the minimum permissions necessary for all files and folders. |
| Weak or no password | • Many people choose a weak password or do not use passwords at all.<br>• It is especially important to make sure that all accounts, especially the administrator account, have a very strong password. |
| Logging in as administrator | • When a user logs in as an administrator, any program they run will have the privileges of that account.<br>• It is better to log in as a standard user and use the administrator password only to perform certain tasks. |

## Abstraction layers of the hardware

Windows use many different types of hardware. The SO can be installed in a built-in computer or assembled by the user.

<u>Basic Windows architecture</u>

<!-- Image-->

A layer of hardware abstraction (HAL) is a software that manage all the communication between the hardware and the kernel. The kernel is the core of the operative system and controls all the computer.

It handles all input and output requests, the memory and all the peripherals connected to it. In some cases, the core still communicates directly with the hardware, so it is not completely independent of the HAL. The HAL also nees the kernel to perform some functions.

## User & kernel mode

There are 2 different modes in which a CPU corks when the computers haves Windows installed: user mode and kernel mode.

The installed applications runs in user mode, and the code of the SO runs in kernel mode. The code that runs in kernel mode haves unlimited access to the underlying hardware and is capable of execute any CPU instructions.

The codes in kernel mode also can do reference to any memory direction directly. An error in the code that runs in kernel mode stops all the system.

But the rest of the programs run in user mode and doesn't have direct access to the hardware memory locations. Due to the error isolation, in this mode only affects to the application and haves a posible recovery.

## Windows file system
A file system determines how information is organized on storage media. Some files systems may be a better choice than others, depending on the type of media used.

### NTFS File system

NTFS is the standard Windows file system, valued for supporting large files and partitions, data recovery, and built-in security (access permissions and encryption). Its timestamps also help reconstruct file activity in forensic investigations.

Structure of an NTFS partition:

Boot sector: locates the Master File Table
MFT: stores file/directory locations, attributes, permissions, and timestamps
System files: hold volume information
File area: stores the actual files and directories

Security note: Formatting does not guarantee data erasure, so a secure wipe is recommended before reusing a drive.

Alternate Data Streams (ADS)

NTFS lets files carry hidden extra data streams (e.g., Testfile.txt:ADS). They don’t appear in a normal dir listing, but can be revealed with dir /r. This makes ADS a known technique for hiding malicious code, which is relevant in malware analysis.

Windows Boot Process

1. Firmware phase

BIOS: runs POST, then finds the MBR to load the OS.
UEFI: modern replacement; loads .efi files from the EFI System Partition, with no MBR dependency and improved security.

2. Bootmgr.exe: switches the CPU from real mode to protected mode and reads the BCD to determine the boot type.

3. Boot type

Hibernation resume: winresume.exe restores the state from Hiberfil.sys.
Cold boot: Winload.exe takes over.

4. Winload.exe: builds the hardware configuration registry and verifies that drivers are digitally signed (KMCS).

5. Ntoskrnl.exe: starts the kernel and configures the HAL, which lets the OS interact with hardware without depending on hardware-specific details.

6. SMSS and Winlogon: SMSS reads the registry to build the user environment, starts Winlogon, and prepares each user’s desktop at login.
