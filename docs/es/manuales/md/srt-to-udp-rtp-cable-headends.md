# SRT → UDP/RTP para cabeceras de cable (ES)

> Conversión a Markdown del PDF original (SRT_to_UDP-RTP_for_cable_headends_SPA.pdf).

<!-- Página 1 -->

## Srt To Udp/Rtp For Cable Headends

## Introducción

Vamos a mostrar la configuración típica que usan los operadores de cable
en sus headends para incorporar señales que entran por SRT desde el LAN1
por Internet, y que salen por UDP/RTP multicast por el LAN2.

El equipo que estamos mostrando para las pruebas es un Minisforum GK41
con 2 puertos LAN, donde el de ethernet más cercano al power cable es el
LAN1 y el más lejano (al lado del HDMI) es el LAN2.

Se supone que el LAN1 se conectará al Gateway con Internet que en este
ejemplo llevará la IP 192.168.1.1 y al LAN1 le pondremos la IP estática
192.168.1.99/24.

Al LAN2 como vamos a conectarlo a la red multicast por un switch con IGMP
snooping y quizás IGMP querier, le pondremos la IP estática
10.10.134.150/24, y no hará falta ponerle ningún Gateway.
Veamos como queda todo configurado en la pestaña Network.
Si su red tiene IPv6 con SLAAC, es posible que le aparezca el modo AUTO, y
unas direcciones fijadasen address y Gateway.
En el LAN2, aunque el placeholder muestre la dirección 192.168.1.1
shadowed, no se está aplicando.

---

<!-- Página 2 -->

Ahora vamos a configurar la entrada SRT Listener por el LAN1 que en
nuestro caso es el interfaz enp2s0 cuya IP es 192.168.1.99

---

<!-- Página 3 -->

Si quiere usar el modo caller, pondrá la IP del servidor SRT de Internet al
que conectarse, y hará la conexión por el LAN1 que es el que tiene el
default Gateway. Para el modo Listener, si no pone ningún Address, o pone
0.0.0.0 o :: , el SRT podrá entrar por cualquiera de las LANs del equipo.
Ponemos la IP del LAN1 para asegurar que solamente conecta por él.

Ahora vamos a configurar la salida por UDP/RTP el multicast por el LAN2.

---

<!-- Página 4 -->

Para ello, vamos a usar la dirección multicast 239.2.2.2:5000 y tenemos que
fijar que va a salir únicamente por el LAN2 con IP 10.10.134.150 .Para ello
ponemos en el Address 10.10.134.150@239.2.2.2 , fijamos también el
puerto el el UDP type en multicast.

Ahora los paquetes UDP/RTP saldrán únicamente por el LAN2 hacia la red
multicast.

---

<!-- Página 5 -->

¿Entonces la salida va en UDP o en RTP?

OnPremise SRT server es transparente al empaquetado, de manera que no
modifica las cabeceras, ni las borra, ni las crea, por lo que si lo que llega por
SRT son empaquetados con cabeceras RTP, eso mismo es lo que saldrá por
la salida UDP. RTP al fin y al cabo no es otra cosa, que paquetes UDP con
cabeceras específicas para redes específicas como MPEG-TS, Barix, Dante,
Ravena, etc. OnPremise respeta estas cabeceras bit a bit, sin modificación
alguna.

Si desea crear en origen es RTP sobre SRT, entonces puede usar OnPremise
SRT en origen, con una entrada UDP que recogerá los paquetes con las
cabeceras originales de RTP y las empaquetará en SRT para que salgan por
SRT hacia Internet.
