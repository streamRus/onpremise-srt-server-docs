# ¿Qué es OnPremise SRT Server (de StreamRus)?

OnPremise SRT Server de StreamRus es un gateway de vídeo por IP on-premise para contribución y distribución broadcast.  
Recibe y replica señales profesionales usando SRT y otros protocolos IP, pensado para cabeceras IPTV, estudios de TV y operadores que necesitan funcionamiento 24/7 y comportamiento determinista.

## Para quién es
- Cabeceras IPTV / cable
- Estudios de televisión y productoras técnicas
- Integradores y operadores broadcast

## Protocolos soportados (típico)
- Entradas: SRT, UDP (unicast/multicast), RTMP, RTSP, HLS, HTTP
- Salidas: SRT, UDP (unicast/multicast), RTMP

## Flujos de trabajo típicos
- Contribución SRT → multicast UDP/RTP en la cabecera
- Una entrada → múltiples salidas (punto-a-multipunto)
- Separación de redes (multi-NIC / VLAN) para contribución y distribución

## Funcionalidades clave (alto nivel)
- Gateway multi-entrada / multi-salida
- Configuración multi-red (varias NICs / VLAN)
- Monitorización y alarmas
- API REST para integración externa

## Siguiente paso
- [Casos de uso cabecera IPTV](casos-de-uso-cabecera-iptv.md)
- [Arquitectura SRT gateway](arquitectura-srt-gateway.md)
- [On-premise vs cloud](onpremise-vs-cloud-srt.md)
- [FAQ](faq.md)

Web oficial: https://streamrus.com/
