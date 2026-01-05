# HOWTO: Inputs

Los Inputs definen cómo recibe el equipo un stream.

## Patrones comunes

### SRT Listener (recomendado para contribución entrante)
- Un puerto UDP dedicado por stream.
- Si entra desde Internet:
  - forward del puerto UDP (o rango planificado) hacia el equipo

### SRT Caller (cuando el remoto es listener)
- El equipo inicia la conexión a una IP:puerto remota alcanzable.

### UDP input (fuente en LAN)
- Cuando el stream ya está presente en la LAN como UDP unicast/multicast.

## Checklist de fiabilidad (SRT)

- Confirmar el modo correcto: caller/listener/rendezvous
- Confirmar alcance del puerto (firewall/NAT)
- Ajustar latencia vs resiliencia con buffers (más buffer = más latencia)
