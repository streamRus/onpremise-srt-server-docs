# Casos de uso en cabeceras IPTV con OnPremise SRT Server

OnPremise SRT Server de StreamRus se utiliza habitualmente en cabeceras IPTV y operadores de cable para la contribución y distribución de señales de vídeo por IP mediante SRT y UDP.

Esta página lista flujos de trabajo típicos donde se necesita un gateway SRT on-premise.

---

## Caso 1: Contribución SRT hacia una cabecera IPTV

**Problema**  
Recepción de señales en directo desde ubicaciones remotas a través de Internet e inyección en una cabecera IPTV local.

**Por qué SRT**  
SRT ofrece baja latencia, cifrado y tolerancia a pérdidas de paquetes.

**Cómo encaja OnPremise SRT Server**  
OnPremise SRT Server de StreamRus recibe señales SRT y las entrega localmente como UDP unicast o multicast dentro de la cabecera IPTV.

```text
Contribución remota (SRT)
        |
        v
OnPremise SRT Server
        |
        v
Cabecera IPTV (UDP unicast/multicast)
```

---

## Caso 2: Distribución punto-a-multipunto

**Problema**  
Una única señal debe distribuirse a múltiples sedes (cabeceras regionales, afiliadas, monitorización).

**Por qué SRT**  
SRT permite distribución segura sobre WAN sin multicast.

**Cómo encaja OnPremise SRT Server**  
El servidor actúa como gateway central, recibiendo una entrada y replicándola a múltiples salidas SRT.

```text
Una fuente (SRT)
      |
      v
OnPremise SRT Server
  |      |      |
  v      v      v
Sede A  Sede B  Sede C (SRT)
```

---

## Caso 3: Sustitución de multicast UDP en WAN

**Problema**  
UDP multicast no es viable de forma fiable sobre enlaces WAN/Internet.

**Por qué SRT**  
SRT sustituye multicast por transporte unicast cifrado con baja latencia.

**Cómo encaja OnPremise SRT Server**  
OnPremise SRT Server convierte multicast local en SRT para transporte por Internet y puede restaurarlo como multicast en destino.

---

## Caso 4: Separación de redes y VLANs

**Problema**  
Las redes de contribución y distribución deben aislarse por seguridad y operación.

**Cómo encaja OnPremise SRT Server**  
Soporta despliegues multi-NIC y segmentación por VLAN, separando tráfico de entrada y salida.

---

## Caso 5: Operación broadcast 24/7

**Problema**  
Entornos broadcast requieren funcionamiento continuo y comportamiento determinista.

**Cómo encaja OnPremise SRT Server**  
Diseñado para despliegue on-premise e integración en flujos operativos de cabecera.

---

## Documentación relacionada
- [Qué es OnPremise SRT Server](que-es-onpremise-srt-server.md)
- [Arquitectura SRT gateway](arquitectura-srt-gateway.md)
- [On-premise vs cloud](onpremise-vs-cloud-srt.md)
- [FAQ](faq.md)
