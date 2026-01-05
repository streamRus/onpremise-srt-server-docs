# Instalación multired (varias NIC)

Vamos a explicar cómo instalar y configurar OnPremise SRT Server en un entorno con varias interfaces físicas de red, conectadas a diferentes LAN o VLAN (untagged).

## Instalación

Antes de instalar la imagen ISO, es conveniente conectar a la red LAN que tiene acceso a Internet con la **LAN1** del equipo en el que instalamos.

Si no sabemos cuál de ellas es, ponemos una al azar, y durante la instalación, el sistema nos dirá si puede o no configurarla por DHCP. Si no es así, conectaremos otra y volveremos a pedir su configuración automática, hasta que demos con ella.

## Configuración

Al entrar en la pestaña **Network** del panel de OnPremise SRT Server, pulsamos sobre **LAN/WLAN Interfaces**, y si aparece vacío, vamos a cualquier otra pestaña y volvemos: la configuración de la red debe haberse cargado.

Veremos la **LAN1** conectada y configurada por DHCP. El resto de interfaces aparecerá vacío, sin ninguna IP asignada.

Solamente necesitamos asignar una **IP y máscara** a cada una de ellas. No hace falta asignar **Gateways**.

Para ello, tenemos que tener claro qué IP vamos a asignar a cada una de acuerdo con qué LAN o VLAN van a conectarse.

En el ejemplo se usan:
- `192.168.100.44/24`
- `192.168.110.44/24`
- `192.168.120.44/24`

Es tan simple como poner las direcciones IP en sus sitios correspondientes e ir pulsando su botón **Save** para guardarla.

Una vez configuradas todas las interfaces LAN disponibles, vamos a **System** y pulsamos sobre **Reboot** para reiniciar el equipo con esa configuración de multired.

Ya podremos conectar desde la LAN2 en adelante a sus respectivas subredes.

## Asignación de las interfaces

Cualquier INPUT u OUTPUT que creemos en la pestaña **Streams** puede ser asignado a recibir o enviar paquetes solamente por una de las interfaces disponibles.

Sin embargo, esto es solamente estrictamente necesario en **UDP multicast**. El resto de protocolos usan direcciones unicast, por lo que el sistema sabe mediante las reglas de enrutamiento por dónde recibir o enviar el stream, sin necesidad de especificarlo.

Si en UDP multicast no asignamos la interfaz que va a usar, entenderá que debe escuchar o enviar en todas las interfaces disponibles.

Para asignar la interfaz a usar, lo haremos en el campo **Address** del protocolo poniendo primero la IP del interfaz LAN a usar, seguido de **@**, y seguido de la IP del grupo multicast a usar.

Ejemplo:
Si vamos a enviar tráfico multicast a `238.0.0.5` usando el conector LAN2 que tiene la IP `192.168.100.40`, el **Address** sería:

`192.168.100.40@238.0.0.5`
