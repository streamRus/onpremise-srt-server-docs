# Troubleshooting

Lista de causas típicas cuando un stream no conecta, se corta o no aparece en el receptor.

## 1) SRT no conecta (caller/listener)

Checklist:
- Confirmar el modo correcto en ambos extremos (caller vs listener).
- Confirmar IP/puerto:
  - el caller debe marcar la IP:puerto del listener
- Confirmar alcance por UDP:
  - firewall permite UDP
  - NAT/port-forward configurado (para puertos listener entrantes)
- Evitar conflictos de puertos:
  - una sesión SRT usa un puerto UDP

Prueba rápida:
- Cambiar temporalmente el puerto UDP para descartar conflicto.

## 2) SRT conecta pero es inestable

Causas comunes:
- Pérdida de paquetes o jitter en el camino
- Latencia/buffer demasiado agresivos

Qué hacer (alto nivel):
- Aumentar buffer/latencia para mejorar resiliencia (a costa de latencia).
- Revisar calidad del enlace y congestión.
- Verificar bitrate total vs ancho de banda disponible.

## 3) UDP multicast no se recibe en la LAN

Checklist:
- Confirmar soporte IGMP/multicast en switch/router.
- Confirmar que los receptores se unen al grupo.
- Confirmar grupo multicast/puerto correctos.
- En sistemas con varias NICs, forzar la interfaz:

`IP_INTERFAZ_LOCAL@IP_GRUPO_MULTICAST`

Ejemplo:
`10.10.134.150@239.2.2.2`

## 4) Funciona en local pero no desde Internet (NAT)

Checklist:
- La IP pública pertenece realmente al router (sin CGNAT).
- Rango de puertos UDP forwardeado hacia el equipo.
- ISP/router no bloquea UDP entrante.
- Si no se puede entrada pública, considerar rendezvous según la topología.

## 5) Problemas de licencia

Síntomas:
- Los canales funcionan solo unos minutos
- Canales nuevos no arrancan

Checklist:
- DNS configurado correctamente en Network.
- Conectividad a Internet para contactar con el servidor de licencias.
- El sistema no ha estado desconectado demasiado tiempo.
