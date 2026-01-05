# Ejemplo cabecera: entra SRT → sale UDP/RTP multicast

Caso típico en cabeceras cable/IPTV:

- **LAN1**: lado Internet (contribución SRT desde encoders remotos)
- **LAN2**: LAN de cabecera/IGMP (distribución UDP/RTP multicast)

## Ejemplo de red

LAN1 (Internet / router):
- IP del equipo: `192.168.1.99/24`
- Gateway: `192.168.1.1`
- DNS: configurado (necesario para refresco de licencia)

LAN2 (Cabecera / LAN multicast):
- IP del equipo: `10.10.134.150/24`
- Sin gateway (solo LAN)

## Ejemplo salida multicast

Grupo multicast:
- `239.2.2.2:5000`

Forzar salida por LAN2:
- `10.10.134.150@239.2.2.2`

## Pasos (alto nivel)

1) Crear un **INPUT**:
   - `SRT Listener` en un puerto UDP (dentro del rango planificado)
2) Crear un **OUTPUT**:
   - `UDP` con grupo multicast y puerto
   - Usar `IP_LOCAL@IP_MULTICAST` para fijar la interfaz correcta
3) Enlazar OUTPUT con INPUT y arrancar

## Nota RTP

Si el stream entrante es **RTP sobre UDP**, el relay debería mantener el empaquetado (comportamiento transparente) según el modo de salida seleccionado.
