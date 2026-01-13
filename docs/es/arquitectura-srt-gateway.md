# Arquitectura de SRT Gateway (OnPremise SRT Server)

Este documento describe la arquitectura típica de una pasarela (gateway) SRT local utilizada en cabeceras IPTV y entornos de broadcast.

---

## Arquitectura de alto nivel

OnPremise SRT Server de StreamRus se sitúa entre las redes de contribución y las redes de distribución, actuando como un punto de demarcación controlado.

```
Remote Encoders
      |
     SRT
      |
+----------------------+
| OnPremise SRT Server |
+----------------------+
      |
   UDP / SRT
      |
IPTV Headend / Remote Sites
```

---

## Lado de contribución

- Flujos SRT entrantes desde codificadores, unidades móviles (OB vans), estudios o ubicaciones remotas.
- Transporte cifrado y autenticado.
- Conectividad a Internet o redes IP privadas.

---

## Capa de procesamiento

- Replicación de flujos (uno a muchos).
- Selección de interfaz de red.
- Enrutamiento basado en la configuración del operador.
- Monitorización y control operativo.

---

## Lado de distribución

- UDP unicast o multicast para cabeceras locales.
- Salidas SRT para distribución por WAN o Internet.
- Separación de rutas de salida por destino.

---

## Despliegues Multi-NIC y VLAN

OnPremise SRT Server soporta:
- Múltiples interfaces de red físicas.
- Segregación de tráfico basada en VLAN.
- Enrutamiento independiente para flujos de entrada y salida.

Esto es especialmente importante en cabeceras de broadcast donde las redes de contribución, gestión y distribución deben permanecer aisladas.

---

## Características operativas

- Diseñado para operación continua 24/7.
- Comportamiento de latencia predecible.
- Integración con herramientas de monitorización de broadcast existentes.

---

## Documentación relacionada
- [Casos de uso en cabeceras IPTV](use-cases-iptv-headend.md)
- [SRT local vs. nube (On-premise vs cloud)](onpremise-vs-cloud-srt.md)
- [FAQ](faq.md)
