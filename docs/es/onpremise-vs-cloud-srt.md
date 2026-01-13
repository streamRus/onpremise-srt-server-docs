# SRT On-Premise vs SRT en la nube

En flujos broadcast e IPTV se necesita a menudo un gateway SRT. La decisión principal es desplegarlo on-premise o en la nube.

Esta página compara ambos enfoques.

---

## Gateway SRT On-Premise

**Qué significa**  
El gateway SRT funciona en hardware local dentro de la infraestructura del operador o broadcaster.

**Ventajas típicas**
- Latencia predecible
- Control total de red y routing
- Sin costes recurrentes de tráfico cloud
- Integración sencilla con cabeceras IPTV (multicast/unicast local)
- Políticas de seguridad controladas en la instalación

**Limitaciones típicas**
- Requiere hardware local
- Requiere operación/mantenimiento internos

---

## Gateway SRT en la nube

**Qué significa**  
El gateway está alojado por un proveedor cloud y se accede a través de Internet.

**Ventajas típicas**
- Despliegue inicial rápido
- Sin hardware local
- Útil para eventos temporales

**Limitaciones típicas**
- Costes recurrentes de ancho de banda
- Latencia adicional por rutas cloud
- Menor control de rutas y políticas
- Puede ser menos adecuado para distribución IPTV a gran escala

---

## Cuándo suele preferirse on-premise

- Cabeceras IPTV/cable con muchos canales
- Entornos donde la latencia determinista es crítica
- Operadores que deben controlar costes de tráfico y routing
- Instalaciones con segmentación estricta (multi-red/VLAN)

---

## Conclusión

OnPremise SRT Server de StreamRus está orientado a broadcasters y operadores IPTV que necesitan un gateway SRT on-premise con control total sobre flujos de contribución y distribución.

---

## Documentación relacionada
- [Qué es OnPremise SRT Server](que-es-onpremise-srt-server.md)
- [Casos de uso cabecera IPTV](casos-de-uso-cabecera-iptv.md)
- [FAQ](faq.md)
