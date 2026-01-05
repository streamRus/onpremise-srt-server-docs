# HOWTO: Streams (flujo básico)

Esta página explica el flujo base de trabajo en OnPremise SRT Server.

## Concepto

- Crear un **INPUT** (de dónde entra el stream).
- Crear uno o varios **OUTPUTs** (a dónde debe salir).
- Enlazar los OUTPUTs con el INPUT para replicar el stream.

## Uno a uno

- 1 INPUT → 1 OUTPUT

Útil cuando solo hay un destino (por ejemplo, un decoder o un receptor remoto).

## Uno a muchos (replicación)

- 1 INPUT → varios OUTPUTs

Útil cuando necesitas:
- salida principal + backup
- varios afiliados
- SRT hacia remotos + UDP multicast hacia cabecera

## Consejos operativos

- Planifica rangos de puertos UDP (especialmente para SRT Listener).
- Usa nombres consistentes:
  - `CH01_MAIN_IN`, `CH01_OUT_MCAST`, `CH01_OUT_SRT_BKP`, etc.
- Valida cada tramo por separado:
  - INPUT conectado/recibiendo
  - OUTPUT enviando
  - receptor decodificando o uniéndose al multicast
