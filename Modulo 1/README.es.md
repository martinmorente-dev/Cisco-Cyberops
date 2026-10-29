🌐 [English](README.md) | [Spanish](README.es.md) | [Go back](https://github.com/martinmorente-dev/Cisco-Cyberops)

# Módulo 1 · El peligro

## Escenarios de ataque
Ejemplos de cómo y por qué se atacan las redes.
- **Gemelo malvado (punto de acceso Wi-Fi falso):** un atacante → monta un "Wi-Fi gratis" falso en una cafetería → para secuestrar la sesión de la víctima mientras usa la banca online → acceso a las cuentas bancarias de la víctima.
- **Ransomware mediante phishing:** un atacante → envía un correo falso haciéndose pasar por el CEO con un PDF malicioso → para cifrar los datos de la empresa y exigir un rescate → datos bloqueados y dinero exigido a la empresa.
- **Malware patrocinado por un estado (Stuxnet):** atacantes a nivel de estado-nación → memorias USB infectadas que se propagaron a sistemas Windows y después a los PLC de Siemens → para dañar las centrifugadoras de una instalación de enriquecimiento de uranio en Irán → daño físico a infraestructura crítica.
- **DDoS con botnet de IoT (Dyn, octubre de 2016):** atacantes → infectaron cámaras web, DVR y routers con malware para formar una botnet → para lanzar un DDoS masivo contra el proveedor de DNS Dyn → muchos sitios web populares dejaron de funcionar.

## Agentes de amenazas
Quién realiza los ciberataques (actos intencionales y maliciosos que buscan perjudicar a una persona u organización) y qué los motiva.
- **Aficionados (script kiddies):** tienen poca o ninguna habilidad; usan herramientas existentes o guías de Internet. Algunos son solo curiosos y otros quieren presumir, pero el daño puede ser grave.
- **Hacktivistas:** atacan para apoyar una causa política o social.
- **Grupos del crimen organizado:** atacan para obtener beneficio económico.
- **Agentes patrocinados por un estado:** trabajan para un gobierno o en su nombre, principalmente para robar secretos comerciales y perseguir objetivos políticos globales.
- **Grupos terroristas:** atacan para promover una ideología y causar miedo o interrupciones.

## Impacto de las amenazas
El coste económico total de los ciberataques es difícil de medir, pero las estimaciones sitúan las pérdidas anuales de las empresas en billones de dólares (unos 5 billones de dólares hasta 2024).

### Robo de datos personales (PII, PHI y PSI)
- **PII (información de identificación personal):** cualquier dato que identifique a una persona: nombre, fecha de nacimiento, número de seguridad social, documentos de identidad, números de tarjeta y de cuenta bancaria, dirección, correo electrónico y teléfono. Los delincuentes la venden en la web oscura y la usan para abrir cuentas financieras falsas, tarjetas de crédito o préstamos.
- **PHI (información de salud protegida):** un subconjunto de la PII que se encuentra en los historiales médicos electrónicos. Está regulada por la HIPAA en EE. UU. y protegida por el RGPD en la UE.
- **PSI (información de seguridad personal):** nombres de usuario, contraseñas y otros datos que se usan para acceder a sistemas y servicios. Según un informe de Verizon de 2019, las credenciales robadas fueron la segunda forma más común de vulnerar redes.
- **Brechas reales:** entre 2019 y 2020, tres grandes plataformas (una herramienta de diseño online, una red social china y una empresa de juegos de Facebook) perdieron los datos de 137, 172 y 218 millones de usuarios respectivamente.

### Pérdida de ventaja competitiva
- Las empresas se preocupan por el espionaje corporativo y el robo de propiedad intelectual por parte de la competencia.
- Perder la confianza de los clientes por no proteger sus datos puede perjudicar a una empresa más que perder secretos comerciales.

### Política y seguridad nacional
- **Filtraciones con motivación política:** en febrero de 2016, un hacker publicó datos personales de 20 000 empleados del FBI y 9000 del DHS.
- **Ciberguerra:** Stuxnet es el ejemplo claro de un ataque motivado por la seguridad nacional. Los hackers patrocinados por un estado pueden interrumpir o destruir servicios vitales de una nación enemiga, y atacar su actividad comercial y financiera online puede dañar su economía.
- **Controladores industriales:** similares a los atacados por Stuxnet, también gestionan el caudal de agua en presas y la alimentación de las redes eléctricas, por lo que atacarlos puede tener consecuencias graves.

Los dispositivos IoT inseguros aumentan el riesgo: muchos nunca reciben actualizaciones de firmware, así que una sola vulnerabilidad puede explotarse a gran escala.

## Conclusión clave
Los ataques pueden dirigirse contra personas, empresas o naciones, y la motivación del atacante cambia en cada caso. Hasta los dispositivos conectados cotidianos pueden convertirse en armas si no se actualizan, y la pérdida más valiosa suele ser la confianza, no solo los datos.
