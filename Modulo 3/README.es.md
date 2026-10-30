# Historia de Windows

## Vulnerabilidades en el sistema operativo

Una vulnerabilidad es una imperfección o debilidad que un atacante puede aprovechar para reducir la viabilidad de la información. Para aprovechar una vulnerabilidad del sistema, el atacante necesita utilizar una técnica o herramienta para atacarlo. El atacante puede usar una vulnerabilidad para que el equipo actúe de una forma distinta a aquella para la que fue diseñado.

La siguiente tabla muestra algunas recomendaciones de seguridad comunes del sistema operativo Windows.

| Recomendación | Descripción |
|---|---|
| Protección contra virus o malware | • De manera predeterminada, Windows utiliza Windows Defender para la protección contra el malware.<br>• Windows Defender ofrece un conjunto de herramientas de protección incorporado en el sistema.<br>• Si Windows Defender está desactivado, el sistema es más vulnerable a los ataques y al malware. |
| Servicios desconocidos o no administrados | • Existen muchos servicios que se ejecutan en segundo plano.<br>• Es importante asegurarse de que cada servicio pueda identificarse y sea seguro.<br>• Con un servicio desconocido ejecutándose en segundo plano, la computadora puede ser vulnerable a los ataques. |
| Cifrado | • Cuando los datos no están cifrados, pueden ser fácilmente recopilados y explotados.<br>• Esto es importante no solo para computadoras de escritorio, sino especialmente para dispositivos móviles. |
| Política de seguridad | • Se debe configurar una buena política de seguridad y hacerla cumplir.<br>• Muchos ajustes en los controles de la política de seguridad de Windows pueden evitar ataques. |
| Firewall | • Por defecto, Windows utiliza el Firewall de Windows para limitar la comunicación con dispositivos en la red.<br>• Con el tiempo, es posible que algunas reglas dejen de ser aplicables.<br>• Por ejemplo, podría quedar abierto un puerto que ya no debería estar disponible.<br>• Es importante revisar la configuración del firewall periódicamente para asegurarse de que las reglas sigan siendo aplicables y eliminar las que ya no lo sean. |
| Permisos de archivo y uso compartido | • Estos permisos deben aplicarse correctamente.<br>• Es fácil darle simplemente al grupo "Todos" control total, pero esto permite a cualquier persona hacer lo que quiera con todos los archivos.<br>• Es mejor otorgar a cada usuario o grupo los permisos mínimos necesarios para todos los archivos y carpetas. |
| Contraseña débil o sin contraseña | • Muchas personas eligen una contraseña débil o no utilizan contraseña en absoluto.<br>• Es especialmente importante asegurarse de que todas las cuentas, sobre todo la de administrador, tengan una contraseña muy fuerte. |
| Iniciar sesión como administrador | • Cuando un usuario inicia sesión como administrador, cualquier programa que ejecute tendrá los privilegios de esa cuenta.<br>• Es mejor iniciar sesión como usuario estándar y utilizar la contraseña de administrador solo para realizar determinadas tareas. |

## Capa de abstracción del hardware

Windows utiliza muchos tipos diferentes de hardware. El sistema operativo puede instalarse en un equipo de fábrica o en uno ensamblado por el usuario.

<u>Arquitectura básica de Windows</u>

<!-- Imagen -->

La capa de abstracción del hardware (HAL) es un software que gestiona toda la comunicación entre el hardware y el núcleo (kernel). El kernel es el núcleo del sistema operativo y controla todo el equipo.

Se encarga de todas las solicitudes de entrada y salida, de la memoria y de todos los periféricos conectados. En algunos casos, el kernel sigue comunicándose directamente con el hardware, por lo que no es totalmente independiente de la HAL. La HAL también necesita el kernel para realizar algunas funciones.

## Modo usuario y modo kernel

Existen 2 modos diferentes en los que funciona una CPU cuando el equipo tiene Windows instalado: modo usuario y modo kernel.

Las aplicaciones instaladas se ejecutan en modo usuario, y el código del sistema operativo se ejecuta en modo kernel. El código que se ejecuta en modo kernel tiene acceso ilimitado al hardware subyacente y puede ejecutar cualquier instrucción de la CPU.

El código en modo kernel también puede hacer referencia directamente a cualquier dirección de memoria. Un error en el código que se ejecuta en modo kernel detiene todo el sistema.

En cambio, el resto de los programas se ejecutan en modo usuario y no tienen acceso directo a las ubicaciones de memoria del hardware. Debido al aislamiento de errores, en este modo un fallo solo afecta a la aplicación y existe la posibilidad de recuperación.

## Sistema de archivos de Windows

Un sistema de archivos determina cómo se organiza la información en los medios de almacenamiento. Algunos sistemas de archivos pueden ser una mejor opción que otros, según el tipo de medio utilizado.

### Sistema de archivos NTFS

NTFS es el sistema de archivos estándar de Windows, valorado por admitir archivos y particiones grandes, recuperación de datos y seguridad integrada (permisos de acceso y cifrado). Sus marcas de tiempo también ayudan a reconstruir la actividad de los archivos en investigaciones forenses.

**Estructura de una partición NTFS:**

- **Sector de arranque:** localiza la tabla maestra de archivos (MFT).
- **MFT:** almacena la ubicación, los atributos, los permisos y las marcas de tiempo de archivos y directorios.
- **Archivos del sistema:** guardan información del volumen.
- **Área de archivos:** almacena los archivos y directorios.

**Nota de seguridad:** formatear no garantiza que los datos se eliminen, por lo que se recomienda un borrado seguro antes de reutilizar una unidad.

#### Flujos de datos alternativos (ADS)

NTFS permite que los archivos contengan flujos de datos adicionales ocultos (por ejemplo, `Testfile.txt:ADS`). No aparecen en un listado normal de `dir`, pero pueden revelarse con `dir /r`. Esto convierte a los ADS en una técnica conocida para ocultar código malicioso, lo cual es relevante en el análisis de malware.

## Proceso de arranque de Windows

1. **Fase del firmware**
   - **BIOS:** ejecuta el POST y luego busca el MBR para cargar el sistema operativo.
   - **UEFI:** sustituto moderno; carga archivos `.efi` desde la partición del sistema EFI, sin depender del MBR y con mayor seguridad.

2. **Bootmgr.exe:** cambia la CPU de modo real a modo protegido y lee la BCD para determinar el tipo de arranque.

3. **Tipo de arranque**
   - **Salida de hibernación:** `winresume.exe` restaura el estado desde `Hiberfil.sys`.
   - **Arranque en frío:** toma el control `Winload.exe`.

4. **Winload.exe:** crea el registro de configuración de hardware y verifica que los controladores estén firmados digitalmente (KMCS).

5. **Ntoskrnl.exe:** inicia el kernel y configura la HAL, que permite al sistema operativo interactuar con el hardware sin depender de detalles específicos de este.

6. **SMSS y Winlogon:** SMSS lee el registro para crear el entorno de usuario, inicia Winlogon y prepara el escritorio de cada usuario al iniciar sesión.
