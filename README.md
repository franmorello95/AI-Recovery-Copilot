# AI Recovery Copilot

PoC academica de un ecosistema de automatizacion para screening secundario y priorizacion de posibles oportunidades de recupero en seguros patrimoniales.

## Alcance

- Datos 100% sinteticos.
- Escenario de referencia: BARBUSS RISK Argentina.
- El sistema no determina responsabilidad juridica, fraude ni inicio automatico de recupero.
- La decision critica final queda sujeta a Human-in-the-Loop (HITL).

## Stack

- n8n: orquestacion
- Airtable: persistencia, revisiones, logs y dashboard
- OpenAI GPT-5 Mini: extraccion semantica estructurada
- Gmail: notificaciones
- OpenAI Batch API: procesamiento masivo diferido

## Archivos de entrega

- `docs/AI_Recovery_Copilot_Documentacion_y_Arquitectura.pdf`
- `workflow/AI_Recovery_Copilot_n8n.json`
- `evidence/`: capturas de ejecucion, dashboard, HITL, logs y Batch
- `batch/recovery-copilot-batch.jsonl`
- `batch/batch_output.jsonl`
- `data/`: dataset sintetico utilizado en el stress test

## Airtable Shared View

Vista publica read-only:
https://airtable.com/app0NaukAM8HxwxIu/shr3tHXgXrQMA81Qh

La Interface de dashboard se documenta mediante capturas y video por la limitacion del plan para publicarla de forma abierta.

## Validaciones destacadas

- Stress test con 10 expedientes sinteticos.
- Override por ausencia de tercero.
- Alerta ante posible limitacion contractual.
- HITL desacoplado del procesamiento masivo mediante Airtable como puente persistente.
- OpenAI Batch API ejecutada end-to-end: 8 requests, 8 completados, 0 fallidos.
- Structured Outputs validado en las 8 respuestas Batch.
- Prompt Caching medido: `cached_tokens = 0`; no se atribuye ahorro real a caching.

## Video

Demo de aproximadamente 3 minutos: [AGREGAR LINK FINAL]
