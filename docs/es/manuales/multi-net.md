# Instalación multi-red (ES)

> Conversión a Markdown del PDF original (MULTI-NET_SPA.pdf).

<!-- Página 1 -->

INSTALACIÓN MULTIRED
Introducción
Vamos a explicar como instalar y configurar OnPremise SRT Server en un entorno con varias
interfaces físicas de red, conectadas a diferentes LAN o VLAN (untagged).
Instalación
Antes de instalar la imagen ISO, es conveniente conectar a la red LAN que tiene acceso a Internet
con la LAN1 del equipo en el que instalamos. Si no sabemos cual de ellas es, ponemos una al azar,
y durante la instalación, el sistema nos dirá si puede o no configurarla por DHCP. Si no es así,
conectaremos otra y volveremos a pedir su configuración automática, hasta que demos ella.
Configuración
Al entrar en la pestaña Network del panel de OnPremise SRT Server, pulsamos sobre LAN/WLAN
Interfaces, y si aparece vacío, vamos a cualquier otra pestaña y volvemos, la configuración de la red
debe de haberse cargado. En ella veremos la de la LAN1 conectada y configurada por DHCP.
Este es un ejemplo:
El resto de interfaces, aparecerá vacío, sin ninguna IP asignada. Solamente necesitamos asignar una
IP y máscara a cada una de ellas. No hace falta asignar Gateways.
Para ello, tenemos que tener claro qué IP vamos a asignar a cada una de acuerdo a con qué LAN o
VLAN van a conectarse.
En nuestro ejemplo vamos a hacer con las IP:
192.168.100.44/24
192.168.110.44/24
192.168.120.44/24

---

<!-- Página 2 -->

Es tan simple, como poner las direcciones IP, en sus sitios correspondientes e ir pulsando su botón
Save para guardarla.
Una vez, configuradas todas las interfaces LAN disponibles, vamos a System y pulsamos sobre
Reboot para reiniciar el equipo con esa configuración de multi-red.
Ya podremos conectar desde la LAN2 en adelante a sus respectivas subredes.

---

<!-- Página 3 -->

Asignación de las interfaces
Cualquier INPUT o OUTPUT que creemos en la pestaña Streams, puede ser asignado a recibir o
enviar paquetes solamente por una de las interfaces disponibles. Sin embargo, esto es solamente
estrictamente necesario en UDP multicast. El resto de protocolos usan direcciones unicast, por lo
que el sistema sabe mediante las reglas de enrutamiento, por donde recibir o enviar el stream, sin
necesidad de especificarlo.
Si en UDP multicast no asignamos la interfaz que va a usar, entenderá que debe escuchar o enviar
en todas las interfaces disponibles. Para asignar la interfaz a usar, lo haremos en el campo Address
del protocolo poniendo primero la IP del interfaz LAN a usar seguido de @ y seguido de la IP del
grupo multicast a usar.
Ejemplo:
Pongamos que vamos a enviar tráfico multicast a 238.0.0.5 usando el conector LAN2 que en
nuestro ejemplo tiene la IP 192.168.100.40. Address entonces sería 192.168.100.40@ 238.0.0.5 .

---

<!-- Página 4 -->

Palabras finales
De esta manera podemos recoger un stream desde una LAN por un INPUT y enviarla a otra u otras
LANs por otro/s OUTPUT, sin ningún límite. Es indiferente de qué LAN recoge un INPUT su
stream, ni a qué LAN los envía un OUTPUT. El funcionamiento es igual de sencillo, de manera que
lo que entra por un INPUT se copia inmediatamente en todos sus OUTPUT asociados, tal como
explicamos en el manual HOWTO.
TodoStreaming 2021
