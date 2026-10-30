# Windows History

## Vulnerabilities in the SO

A vulnerability is an imperfection or weakness that it could be used by an attacker to reduce the viability of information. To take advantage over a system vulnerability, the attacker need to use a technique or tool to attack it. The attacker can use a vulnerability for the computer to act in a different way that isn't design for.

The next table show some common security recommendations of the windows SO.


| Recomendación | Descripción |
|---|---|
| Protección contra virus o malware | • De manera predeterminada, Windows utiliza Windows Defender para la protección contra el malware<br>• Windows Defender ofrece un conjunto de herramientas de protección incorporado en el sistema.<br>• Si Windows Defender está desactivado, el sistema es más vulnerable a los ataques y al malware. |
| Servicios desconocidos o no administrados | • Existen muchos servicios que se ejecutan en segundo plano.<br>• Es importante asegurarse de que cada servicio pueda identificarse y sea seguro.<br>• Con un servicio desconocido ejecutándose en segundo plano, la computadora puede ser vulnerable a los ataques. |
| Cifrado | • Cuando los datos no se encuentran encriptados pueden ser fácilmente reunidos y explotados.<br>• Esto no es solamente importante para computadoras de escritorio, sino especialmente para dispositivos móviles. |
| Política de seguridad | • Se debe configurar una buena política de seguridad y debe cumplirse.<br>• Muchos ajustes en el control de la política de seguridad de Windows pueden evitar ataques. |
| Firewall | • Por defecto, Windows utiliza el Firewall de Windows para limitar la comunicación con dispositivos en la red<br>• Con el tiempo, es posible que las reglas ya no se apliquen.<br>• Por ejemplo, podría dejarse abierto un puerto que ya no debe estar disponible.<br>• Es importante revisar la configuración del firewall periódicamente para asegurarse de que las reglas sigan siendo aplicables y eliminar las que ya no se apliquen. |
| Permisos de archivo y uso compartido | • Estos permisos deben ser aplicados correctamente.<br>• Es fácil solo darle al grupo “Todos” control total, pero esto permite a todas las personas realizar lo que ellas quieran con todos los archivos.<br>• Es mejor otorgar a cada usuario o grupo los permisos mínimos necesarios para todos los archivos y carpetas. |
| Contraseña débil o sin contraseña | • Muchas personas eligen una contraseña débil o no utilizan contraseñas del todo.<br>• Es especialmente importante asegurarse de que todas las cuentas, especialmente la cuenta de administrador, tengan una contraseña muy fuerte. |
| Iniciar sesión como administrador | • Cuando el usuario inicia sesión como administrador, cualquier programa que ejecuten tendrá los privilegios de esa cuenta.<br>• Es mejor iniciar sesión como un usuario estándar y utilizar solamente la contraseña de administrador para realizar determinadas tareas. |


## Abstraction layers of the hardware

Windows use many different types of hardware. The SO can be installed in a built-in computer or assembled by the user.

<u>Basic Windows architecture</u>

<!-- Image-->

A layer of hardware abstraction (HAL) is a software that manage all the communication between the hardware and the kernel. The kernel is the core of the operative system and controls all the computer.

It handles all input and output requests, the memory and all the peripherals connected to it. In some cases, the core still communicates directly with the hardware, so it is not completely independent of the HAL. The HAL also nees the kernel to perform some functions.

## User & kernel mode

There are 2 different modes in which a CPU corks when the computers haves Windows installed: user mode and kernel mode.

<!-- Image-->

The installed applications runs in user mode, and the code of the SO runs in kernel mode. The code that runs in kernel mode haves unlimited access to the underlying hardware and is capable of execute any CPU instructions.

The codes in kernel mode also can do reference to any memory direction directly. An error in the code that runs in kernel mode stops all the system.

But the rest of the programs run in user mode and doesn't have direct access to the hardware memory locations. Due to the error isolation, in this mode only affects to the application and haves a posible recovery.

## Windows file system
A file system determines how information is organized on storage media. Some files systems may be a better choice than others, depending on the type of media used.

<!-- image -->

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
