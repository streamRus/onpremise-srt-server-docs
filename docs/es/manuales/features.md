# Características (ES)

> Conversión a Markdown del PDF original (FEATURES_SPA.pdf).

<!-- Página 1 -->

ON PREMISE SRT SERVER
OnPremise SRT Server es una solución completa de software y sistema operativo, que convierte
una computadora compatible en un disruptivo servidor multimedia en sus propias dependencias,
capaz de replicar multiples entradas en multiples salidas, como se muestra en el gráfico superior
(punto a punto y punto a multipunto)
Fácil de controlar desde un navegador web, desde cualquier computador conectado a la red.
Construirá su red de contibución / distribución en unos pocos clics, y lo controlará todo 24/7 en
tiempo real. Bloquear y desbloquear componentes individuales (entradas o salidas), asignar un
watchdog a cualquier origen para avisarle de la carencia de audio, alertándole de cualquier
problema del lado de la fuente.

---

<!-- Página 2 -->

Abajo listamos las características:
- Protocolos de entrada: RTMP/S pull, RTSP pull, HTTP pull, HLS, DASH, UDP
(unicast/multicast), SRT (caller/listener/rendezvous)
- Protocolos de salida: UDP(unicast/multicast), SRT(caller/listener/rendezvous), RTMP/S(Youtube,
Facebook, Twitch, Wowza y muchos más…)
- UDP y SRT Transport Streams originales, se repetirán exactamente tal como son, sin añadir
latencia, y sin cambiar ni un solo bit (ni remultiplexar)
- UDP y SRT son agnósticos al codec y a la resolution, por lo que podrán transportar MPEG-2,
H.264/AVC, H.265/HEVC, H.266/VVC o cualquier otro codec TS compatible. Podrán enviar tanto
SPTS como MPTS. Cualquier resolución: SDTV, HDTV, 4K, 8K.
- Controle el estado de toda su red de TV/Radio de un solo vistazo y en tiempo real
(conectados/disconectados, alarmas de watchdog, etc)
-
Icono de acceso remoto asignable a una http URL remota para controlar cualquier elemento
de la red desde el mismo panel en un solo clic
- Puede borrar y editar cualquier elemento de la red, y también reasignar una salida a cualquier otra
entrada inmediatamente
- Copia de seguridad y restauración de todos los componentes de la red, y ajustes a/desde un fichero
JSON
- Fácilmente actualizable en un solo clic
- DDNS para DynDNS y No-IP
- IPv4 e IPv6 en doble pila
- MDNS (Bonjour) integrado, para descubrir la IP de su equipo de manera facil y rápida
- UPnP para abrir cualquier puerto de su router a internet dinámicamente (si es compatible con
libminiupnpc)
- Basado en Debian 10, el sistema es lo suficientemente seguro y estable para estar en su zona DMZ
- Roles de admin y usario (posibilidad de bloqueo del usuario por parte del admin)
- API REST disponible y documentada en Swagger 2.0 (crea tu propio panel front-end con tu
marca, o crear una App externa para controlar todo el sistema)
- 1 mes gratis para toda nueva instalación de hardware
Requisitos mínimos del Hardware:
- PC x64 (64 bits)
- CPU 4 nucleos 1.5 GHz (40 streams), 8 nucleos 3.0 GHz (+128 streams)
- 4 GB RAM (40 streams), 8 Gbs (128 streams)
- 32 GB de disco duro o más
- 1 Gbps puerto de red LAN
Ejemplo de CPU para 40 streams (200 Mbps): Intel Atom x5-Z8350 (Minisforum Z83-F)
Ejemplo de CPU para 128 streams (600 Mbps): Intel Pentium Gold G5420 3.8 GHz
Ejemplo de CPU para 256 streams (1 Gbps): Intel Core i3-10320 (8HT x 3.8 GHz)
Desarrollado por TodoStreaming (2020)
