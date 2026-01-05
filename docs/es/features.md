# Características (alto nivel)

## Entradas (ejemplos)

- RTMP/S pull
- RTSP pull
- HTTP pull
- HLS
- DASH
- UDP

## Salidas (ejemplos)

- UDP (unicast/multicast)
- SRT (caller/listener/rendezvous)
- RTMP/S (por ejemplo, YouTube)

## Transporte

- UDP y SRT mantienen el Transport Stream original (sin añadir modificaciones).
- UDP y SRT son agnósticos al códec y a la resolución (pueden transportar MPEG-2, etc.).

## Operación

- Control del estado en tiempo real.
- Edición/borrado de elementos y reasignación de salidas.
- Copia de seguridad y restauración desde/hacia fichero.
- Actualización en un clic.

## Red / sistema

- DDNS (DynDNS / No-IP)
- Doble pila IPv4 e IPv6
- mDNS (Bonjour) para descubrir IP
- UPnP (si el router es compatible)

## Usuarios / API

- Roles de admin y usuario
- API REST documentada en Swagger 2.0
