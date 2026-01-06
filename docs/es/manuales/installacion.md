# Instalación (ES)

> Conversión a Markdown del PDF original (INSTALL_SPA.pdf).

<!-- Página 1 -->

ON PREMISE SRT SERVER INSTALACION
Una vez seleccionado el computador donde instalar el sistema OnPremise SRT Server, debe
tener en cuenta que toda la información contenida en el disco duro del mismo será
completamente borrada y reemplazada por el nuevo sistema.
NO FUNCIONA EN MAQUINAS VIRTUALES, SOLO EN HARDWARE REAL
Pasos a seguir:
1.- Descargue la imagen ISO comprimida en zip, y descomprimala en una carpeta.
2.- Puede grabar el contenido del ISO en un disco óptico o en un USB que pueda borrar su
contenido. El contenido del ISO es inferior a los 500 MB, por lo que debe caber en cualquier
almacenamiento mayor a esta cantidad.
a) Disco óptico. Puede usar BurnAware o cualquier otro, y seleccionar “Record ISO”(Grabar ISO)
b) USB drive. Puede usar Rufus v3.13 o superior.
Una vez que el USB ha sido pinchado, pulse Seleccionar, y elija el fichero ISO descomprimido.
Pulse Empezar y luego elija el modo de Image DD. Acepte la advertencia de borrado de datos.
Una vez grabado, una barra VERDE de estado aparecerá con el mensaje PEPARADO. Ahora puede
desconectar el USB drive. Ya estamos preparados para iniciar la instalación en el equipo elegido.

---

<!-- Página 2 -->

3.- Primero de todo, tendremos que entrar en la BIOS del equipo objetivo, para cambiar el orden de
arranque (Boot), y permitir que el USB inicie primero.
4.- Cuando la imagen ISO arranca, verá el siguiente menú:
El izquierdo corresponde a la instalación desde disco óptico. El de la derecha al USB grabado con
Rufus, que añade opciones adicionales al menú original.
SIEMPRE seleccionaremos Install y pulsaremos la tecla ENTRAR
Elija su idioma, país y configuración de teclado deseado:
El proceso de instalación comenzará. Ponga un nombre descriptivo para su equipo en Hostname, y
pude dejar en blanco la opción de Domain name (dominio) si no dispone de un servidor de DNS
interno en su red local.
Seleccione su zona horaria.
Si el disco duro del equipo objetivo no esta vacío, aparecerá esta ventana de error, es normal:

---

<!-- Página 3 -->

Elija Go Back (retroceder), y seleccione Detectar discos y presione la tecla ENTRAR.
Luego seleccione Guiado-usar el disco completo.
Seleccione el disco duro del equipo objetivo (el segundo es nuestro USB drive)
La instalación contniuará, hasta la pregunta “Escanear otro CD o DVD?”, diremos que NO.
Finalmente si le pregunta donde grabar el boot loader, elija el disco destino (nunca manualmente).

---

<!-- Página 4 -->

Aparecerá la última pantalla de instalación. Pulse continuar y ya habremos terminado.
El computador objetivo reiniciará y mostrará un pantalla con un cuadrado grande AZUL. Espere
hasta que el proceso acabe en una pantalla negra con el prompt de login. Ahora el sistema se
autoconfigurará llevando acabo procesos internos por menos de 1 minuto, y reiniciará de nuevo.
Después de este segundo inicio, nos llevará directamente a la ventana negra con el login y el
nombre que pusimos en el hostname.
El proceso de instalación ha terminado. Es el momento de entrar al panel de control.
Su sistema OnPremise SRT Server system será accesible desde cualquier equipo de la red con
navegador web, pero antes tendremos que detectar la IP del equipo.
Desde otro equipo de la red,
usaremos Bonjour Browser(http://hobbyistsoftware.com/bonjourbrowser) para esta tarea rápida.

---

<!-- Página 5 -->

En la parte inferior aparece la IP del equipo inmediatamente (en este ejemplo es 192.168.1.24:80, y
puede obviar el :80 del protocolo HTTP que su navegador web ya usa por defecto)
Username: admin Password: admin (para el rol de administrador)
Username: user Password: user (para el rol de usuario)
No olvide cambiar los passwords por seguridad, y guardar el e-mail de recuperación.
Ya puede empezar a utilizar su nuevo OnPremise SRT Server system.
Que se divierta !!!
IMPORTANTE: Antes de empezar a trabajar, vaya a la pestaña License y asegúrese de que el
equipo esta conectado con nuestro servidor de licencias y de que tiene una licencia LICA-G
gratuita para los próximos 30 días. Si esto no es así, los canales nuevos que cree solamente
funcionarán durante 5 minutos y nada más. Configure un DNS válido en la pestaña Network, para
asegurar la conexión con el servidor de licencias, y la bajada de una nueva clave para los
siguientes 7 días. No desconecte su servidor de Internet más de 7 días o éste quedará bloqueado.
2020 TodoStreaming
