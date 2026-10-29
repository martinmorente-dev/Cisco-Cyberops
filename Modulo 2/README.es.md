🌐 [English](README.md) | [Spanish](README.es.md)


# Módulo 2 · Combatientes en la guerra contra la ciberdelincuencia

## Elementos de un SOC
Un Centro de Operaciones de Seguridad (SOC) es un equipo de profesionales que defiende a una organización frente a las amenazas actuales con un enfoque formal y estructurado. Sus servicios van desde la monitorización y la gestión hasta soluciones completas de protección contra amenazas y seguridad alojada. Un SOC puede ser interno o externalizarse a un proveedor de seguridad (por ejemplo, Cisco Managed Security Services).

Sus tres elementos principales son:
- **Personas:** los profesionales que trabajan en el SOC, organizados por roles y niveles.
- **Procesos:** cómo detecta y responde a los incidentes.
- **Tecnología:** las herramientas con las que monitoriza y defiende.

## Personas en el SOC
Los roles en un SOC evolucionan rápido. Actualmente, estos son los roles del equipo:

- **Analista de alertas (nivel 1):** monitoriza las alertas de entrada, verifica si son un incidente real y, si lo son, escala el ticket al nivel 2.
- **Respuesta a incidentes (nivel 2):** se encarga de investigar a fondo los incidentes y de recomendar soluciones o acciones.
- **Cazadores de amenazas (nivel 3):** tienen un nivel experto en redes, dispositivos finales (endpoints), inteligencia de amenazas e ingeniería inversa de malware.
- **Administrador del SOC:** gestiona todos los recursos del SOC y es el punto de contacto con el resto de la organización.

## Procesos en el SOC
La jornada de un analista de ciberseguridad empieza con la monitorización de una cola de alertas de seguridad. Como el sistema puede generar falsas alertas, una de sus tareas es verificar si cada alerta es real o no.

Si el ticket corresponde a un incidente real, lo escala al nivel 2 y, después, a los niveles siguientes si no se puede resolver.

## Tecnologías del SOC: SIEM
Un SOC necesita un sistema **SIEM (Security Information and Event Management, gestión de información y eventos de seguridad)** o equivalente. Da sentido a todos los datos que generan los firewalls, los dispositivos de red, los sistemas de detección de intrusiones y otros dispositivos.

Un SIEM sirve para:
- Recopilar y filtrar datos.
- Detectar y clasificar amenazas.
- Analizar e investigar amenazas.
- Gestionar recursos para aplicar medidas preventivas y afrontar amenazas futuras.

Las tecnologías del SOC cubren una o varias de estas áreas:
- **Recopilación, correlación y análisis de eventos:** reunir eventos de muchas fuentes y relacionarlos para detectar patrones sospechosos.
- **Monitorización de la seguridad:** vigilar el entorno de forma continua para detectar incidentes.
- **Control de la seguridad:** gestionar las medidas que protegen los sistemas.
- **Administración de registros (logs):** almacenar y organizar los logs para poder revisarlos después.
- **Evaluación de vulnerabilidades:** encontrar debilidades en los sistemas antes que los atacantes.
- **Seguimiento de vulnerabilidades:** controlar cada debilidad hasta que se corrige.
- **Inteligencia de amenazas:** usar información sobre amenazas y atacantes actuales para anticipar ataques.

## Tecnologías del SOC: SOAR
SIEM y SOAR suelen ir juntos porque sus capacidades se complementan. Los grandes equipos de operaciones de seguridad (SecOps) usan ambas tecnologías para optimizar su SOC.

Las plataformas SOAR se parecen a los SIEM en que recopilan, correlacionan y analizan alertas. La diferencia es que SOAR va un paso más allá: integra inteligencia de amenazas y automatiza los flujos de investigación y respuesta a incidentes basándose en **playbooks** desarrollados por el equipo de seguridad.

Una plataforma SOAR:
- Recopila datos de alarma de cada componente del sistema.
- Ofrece herramientas para investigar, evaluar y analizar casos.
- Se centra en la integración para automatizar los flujos de respuesta a incidentes complejos, lo que permite una respuesta más rápida y estrategias de defensa adaptadas.
- Incluye playbooks predefinidos para responder automáticamente a amenazas concretas. Pueden iniciarse solos según reglas predefinidas o activarlos el personal de seguridad.

**Por qué importa:** un SIEM genera más alertas de las que la mayoría de los equipos SecOps pueden investigar de forma realista. SOAR procesa muchas de ellas automáticamente y deja el trabajo manual para los casos que de verdad requieren a una persona, de modo que los analistas se centran en amenazas más complejas y potencialmente más dañinas.

## Métricas del SOC
Entender qué tan bien funciona un SOC es clave para mejorar a las personas, los procesos y las tecnologías que lo componen. Se pueden diseñar muchas métricas o indicadores clave de rendimiento (KPI), pero cinco se usan habitualmente. Hay que tener en cuenta que las métricas de rendimiento general a menudo no muestran una imagen precisa del funcionamiento real de un SOC, por la diversidad de amenazas de ciberseguridad.

- **Tiempo de permanencia (dwell time):** el tiempo que los actores de amenazas tienen acceso a una red antes de ser detectados y de que se detenga su acceso.
- **Tiempo medio de detección (MTTD):** el tiempo medio que tarda el personal del SOC en identificar que se han producido incidentes de seguridad válidos en la red.
- **Tiempo medio de respuesta (MTTR):** el tiempo medio que se tarda en detener y corregir un incidente de seguridad.
- **Tiempo medio para contener (MTTC):** el tiempo necesario para evitar que el incidente cause más daños a los sistemas o a los datos.
- **Tiempo de control:** el tiempo necesario para detener la propagación de malware en la red.

## Seguridad empresarial y administrada
Las redes medianas y grandes se benefician de un SOC de nivel empresarial. Puede ser una solución totalmente interna, pero muchas organizaciones grandes externalizan al menos una parte de sus operaciones a un proveedor de seguridad.

Como ejemplo de lo que puede ofrecer un proveedor, Cisco cuenta con equipos de expertos que ayudan a resolver incidentes de forma rápida y precisa, con una gama de capacidades de respuesta, preparación y gestión de incidentes:
- Smart Net Total Care (resolución rápida de problemas).
- PSIRT: equipo de respuesta a incidentes de los productos de Cisco.
- CSIRT: equipo de respuesta a incidentes de seguridad informática.
- Servicios administrados.
- TacOps: operaciones tácticas.
- Programa de seguridad física.

## DevSecOps
DevSecOps significa Desarrollo, Seguridad y Operaciones. Es la práctica de integrar la seguridad en el proceso de DevOps, de modo que forme parte de todo el ciclo de vida del software en lugar de añadirse al final. Al incorporarla desde el principio, se busca reducir las vulnerabilidades y mejorar la seguridad general de las aplicaciones, los sistemas y los entornos.

Lo que aporta:
- **Remediación más rápida:** los problemas de seguridad se detectan pronto, lo que reduce el tiempo y el coste de solucionarlos.
- **Riesgo reducido:** las comprobaciones de seguridad continuas disminuyen la probabilidad de que las vulnerabilidades lleguen a producción.
- **Mayor eficiencia:** automatizar las tareas de seguridad permite a los equipos centrarse en sus responsabilidades principales sin descuidar la seguridad.
- **Mejor colaboración:** la seguridad es una responsabilidad compartida, lo que mejora la comunicación entre desarrolladores, equipos de seguridad y de operaciones.

El objetivo es crear una cultura de seguridad donde todos sean responsables de ella en cada fase del desarrollo, para construir software más seguro, mitigar riesgos con más rapidez y tener una infraestructura más resiliente.

## Seguridad frente a disponibilidad
La mayoría de las redes empresariales tienen que estar funcionando en todo momento, así que el personal de seguridad sabe que mantener la red disponible es clave para cumplir las prioridades de la organización.

Cada empresa tiene una tolerancia limitada al tiempo de inactividad, que suele basarse en comparar el coste de esa inactividad con el coste de protegerse contra ella. Por ejemplo, un comercio pequeño con una sola ubicación puede conformarse con un único router como punto único de fallo. Pero si gran parte de sus ventas son online, el dueño puede decidir añadir redundancia para tener siempre conexión.

El tiempo de actividad se suele medir como el tiempo de inactividad al año, expresado en "nueves":

| Disponibilidad | Inactividad al año |
|---|---|
| 99,8 % | 17,52 horas |
| 99,9 % ("tres nueves") | 8,76 horas |
| 99,99 % ("cuatro nueves") | 52,56 minutos |
| 99,999 % ("cinco nueves") | 5,256 minutos |
| 99,9999 % ("seis nueves") | 31,56 segundos |
| 99,99999 % ("siete nueves") | 3,16 segundos |

**Idea clave:** el nivel de seguridad no debe ser tan alto como para interferir con las necesidades de los empleados o las funciones de la empresa. Se trata de lograr un equilibrio entre un buen nivel de seguridad y que la empresa pueda funcionar con eficacia.