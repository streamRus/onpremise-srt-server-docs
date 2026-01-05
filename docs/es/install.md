# Instalación (ISO)

Importante: instalar la ISO de OnPremise SRT Server **borra por completo el disco** del equipo donde lo instalas.

**No funciona en máquinas virtuales. Solo hardware real.**

## Pasos

1) Descarga la imagen ISO (en ZIP) y descomprímela.
2) Graba la ISO en un medio arrancable:
   - Disco óptico: cualquier programa para grabar ISO.
   - USB: Rufus v3.13 o superior y elegir **modo DD Image** cuando lo pida.
3) Arranca el PC objetivo desde el USB/disco e instala.

## Encontrar la IP en la LAN

Usa mDNS/Bonjour para descubrir la IP en la red local.
Ejemplo de herramienta: Bonjour Browser.

Cuando la tengas, abre el panel web en el navegador.

## Credenciales por defecto

- Rol administrador: `admin / admin`
- Rol usuario: `user / user`

Cambia las contraseñas por seguridad y guarda el e-mail de recuperación.

## Nota de licencia (importante)

Antes de crear canales, entra en la pestaña **License** y comprueba que el equipo conecta con el servidor de licencias y que tiene una licencia gratuita de 30 días.

Si no es así, los canales nuevos pueden funcionar solo unos minutos.

Configura un DNS válido en la pestaña **Network** para asegurar la conexión con el servidor de licencias y la descarga de claves.
No desconectes el servidor de Internet más de varios días o podría quedar bloqueado.
