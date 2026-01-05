# SRT básico (caller / listener / rendezvous)

SRT puede funcionar en tres modos de conexión:

## Listener
- El receptor (lado servidor) queda a la escucha en un puerto UDP.
- El emisor conecta como Caller.

Típico:
- Servidor: `srt://0.0.0.0:PUERTO?mode=listener`
- Remoto: `srt://IP_PUBLICA:PUERTO?mode=caller`

## Caller
- El equipo inicia la conexión contra un Listener remoto.
- Útil cuando el destino tiene IP/puerto público alcanzable.

Típico:
- Equipo: `srt://IP_REMOTA:PUERTO?mode=caller`

## Rendezvous
- Ambos extremos inician conexión entre sí.
- Puede ayudar en escenarios NAT donde es complicado recibir conexiones entrantes.

Típico:
- Ambos lados con `mode=rendezvous` y mismas reglas de puertos.

---

## Puertos (importante)

- **Una sesión SRT usa un puerto UDP.**
- Si necesitas muchos streams simultáneos, planifica un rango de puertos UDP.
- Para SRT entrante desde Internet:
  - Forwardea el/los puertos UDP (o rango) hacia la IP del equipo.
  - Evita solapar con otros servicios.

---

## Fiabilidad vs latencia (alto nivel)

SRT puede absorber pérdida/jitter usando buffers y retransmisión.
Compromiso:
- Buffers grandes = más resiliencia, más latencia.
- Buffers pequeños = menos latencia, menos tolerancia a pérdida/jitter.
