# FAQ

## ¿Este repositorio es el software?
No. Este repositorio contiene solo documentación. El software es propietario y se distribuye aparte.

## ¿Puede ejecutarse en una máquina virtual?
Está orientado a despliegues en hardware físico.

## ¿Es un transcodificador?
No. Está pensado como relay/gateway para flujos de contribución y distribución (sin re-encode).

## ¿Puedo hacer punto a multipunto?
Sí. Un INPUT puede alimentar múltiples OUTPUTs.

## ¿Cómo fijo UDP multicast a una NIC concreta?
Usa:
`IP_INTERFAZ_LOCAL@IP_GRUPO_MULTICAST`

Ejemplo:
`10.10.134.150@239.2.2.2`

## ¿Cuántos streams SRT simultáneos soporta?
Depende de CPU/red y del bitrate total. Planifica rangos de puertos y prueba con tráfico real.

## ¿Necesito DNS/Internet?
Sí, en despliegues típicos se requiere DNS/Internet para el refresco de la licencia.
