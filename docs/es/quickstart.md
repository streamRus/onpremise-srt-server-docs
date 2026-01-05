# Inicio rápido

Checklist práctico para dejar un flujo básico SRT ↔ UDP funcionando.

## 1) Encontrar el equipo en la LAN

- Descubre la IP mediante **mDNS/Bonjour** en la red local.
- Abre el panel web en el navegador.

## 2) Primer acceso

- Entra en la web UI.
- Cambia las contraseñas por defecto tras el primer acceso.

## 3) Configuración de red

Recomendado:
- Fijar una **IP estática** fuera del rango DHCP.
- Configurar al menos un **DNS** (necesario para el refresco de licencia).
- Si usas varias NICs, deja el acceso a Internet en una interfaz y usa las demás para LANs dedicadas (por ejemplo, multicast/cabecera).

## 4) Puertos SRT y NAT (si recibes desde Internet)

Si vas a recibir SRT desde sitios remotos por Internet:
- Define un **rango de puertos UDP** para listeners SRT (ej.: 5000–7000).
- Abre/forwardea ese rango UDP en el router/firewall hacia la IP del equipo.
- Asegúrate de que tu IP pública es alcanzable y no hay bloqueo del ISP.

## 5) Crear el primer relay

Patrón típico:
1) Crear un **INPUT**:
   - Ejemplo: `SRT Listener` (lado servidor)
2) Crear un **OUTPUT**:
   - Ejemplo: `UDP multicast` (para LAN de cabecera) o `SRT Caller` (hacia un receptor remoto)
3) Enlazar el OUTPUT con el INPUT y arrancar el flujo.

## 6) Validación rápida

- Confirmar que el INPUT está “connected/receiving”.
- Confirmar que el OUTPUT está “running/sending”.
- Validar en el receptor (decoder, IRD, cabecera, player) que el stream llega.
