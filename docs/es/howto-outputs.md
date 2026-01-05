# HOWTO: Outputs

Los Outputs definen a dónde envía el equipo el stream.

## Salidas SRT

Se usan para contribución/distribución en redes enrutadas (incluida Internet).

Consejos:
- Nombres claros: MAIN / BKP
- Para varios broadcasters, replica con varios outputs

## Salidas UDP (unicast / multicast)

### UDP unicast
- Una IP destino por receptor.

### UDP multicast (cabeceras / distribución en LAN)
- Un grupo multicast para muchos receptores en la misma LAN.

Si tienes varias NICs y quieres forzar la interfaz, usa:

`IP_INTERFAZ_LOCAL@IP_GRUPO_MULTICAST`

Ejemplo:
`10.10.134.150@239.2.2.2`

## Nota RTP sobre UDP

Según el modo de salida seleccionado, el empaquetado puede preservarse en flujos RTP sobre UDP.
