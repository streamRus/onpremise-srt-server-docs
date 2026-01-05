# UDP multicast (unicast / multicast)

Las salidas UDP se usan mucho para distribución en LAN y cabeceras.

## Unicast vs multicast

- **Unicast**: una IP de destino por receptor.
- **Multicast**: una IP de grupo multicast para muchos receptores en la misma LAN (requiere red con IGMP).

## Fijar multicast a una NIC concreta

En despliegues con varias NICs (por ejemplo, Internet en LAN1 y cabecera en LAN2) suele interesar forzar el multicast por una interfaz concreta.

Formato:

`IP_INTERFAZ_LOCAL@IP_GRUPO_MULTICAST`

Ejemplo:

`10.10.134.150@239.2.2.2`

Después se configura el puerto UDP normalmente (por ejemplo `:5000`, según cómo lo pida la UI).

## Notas para cabeceras

- Asegura que la red (switch/router) soporta multicast e IGMP.
- Mantén la distribución multicast dentro de la LAN (no por Internet).
- Valida en un receptor/IRD que se una al grupo.
