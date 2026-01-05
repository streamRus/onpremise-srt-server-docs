# Visión general

OnPremise SRT Server es una solución on-premises (software + imagen de S.O.) orientada a construir y operar flujos profesionales de contribución y distribución broadcast/IPTV.

Se opera desde una interfaz web en la red local y está orientado a ejecutarse en hardware físico x64.

## Concepto base

- Crear **INPUTs** (fuentes): entradas SRT/UDP o fuentes “pull”.
- Crear **OUTPUTs** (destinos): salidas SRT/UDP (unicast/multicast) y flujos tipo gateway.
- Enlazar OUTPUTs con INPUTs para replicar streams (uno a uno o uno a muchos).
- Monitorizar estado y actividad desde el panel web.

## Casos de uso típicos

- Contribución por Internet usando **SRT**.
- Distribución en LAN usando **UDP multicast / RTP sobre UDP** para cabeceras.
- Relay punto a punto y punto a multipunto.
- Despliegues multi-red con varias NICs (separar Internet y redes multicast).

## Qué contiene este repo

Solo documentación, FAQs y notas prácticas. El software es propietario y se distribuye aparte.
