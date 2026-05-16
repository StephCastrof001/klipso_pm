# Agent Review Brief — Clínica Vesalio n8n Flows
Fecha: 2026-04-13

## Contexto del sistema
Sistema multi-agente de WhatsApp para agendamiento médico.
- Orquestador principal: `Clinica Vesalio Optimizado` (69 nodos)
- Sub-agente 1: `AGENTE - Consultas Generales` (12 nodos)
- Sub-agente 2: `AGENTE - Agendar Citas` (42 nodos)
- Utility: `_SAVE_DATA_PROD` (5 nodos)
- Stack: PostgreSQL (session state + chat memory), Redis (dedup), PGVector (RAG), OpenAI

## Tu tarea
Analiza los JSONs de n8n adjuntos y responde cada checklist.
Por cada problema encontrado indica:
- Ubicación exacta: nombre del nodo + workflow
- Severidad: CRÍTICO / MEDIO / BAJO
- Descripción en una línea (sin jerga para PM no técnico)
- Estimación de fix: horas

No expliques cómo funciona n8n. Solo responde los checklists.

---

## CHECKLIST 1 — Session State (_SAVE_DATA_PROD)
Impacto de negocio: si falla, los datos del paciente se corrompen o mezclan entre usuarios.

Preguntas:
- [ ] ¿El UPSERT a PostgreSQL es atómico? ¿Puede haber race condition si llegan 2 mensajes simultáneos del mismo usuario?
- [ ] ¿Qué campos se sobreescriben sin verificar si ya tienen valor?
- [ ] ¿Cuándo se ejecuta CLEAR_DATA? ¿Hay riesgo de limpiar datos antes de que se confirme el booking?
- [ ] ¿Hay algún campo crítico (DNI, teléfono, doctor elegido) que pueda perderse entre nodos?

Output requerido:
```
CHECKLIST 1 — Session State
¿Race condition posible?       sí / no — [nodo]
¿Campos sobreescritos sin check? sí / no — [cuáles]
¿CLEAR_DATA en momento incorrecto? sí / no
¿Pérdida de datos posible?     sí / no — [dónde]
Severidad global: CRÍTICO / MEDIO / BAJO
Estimación de fix: __ horas
```

---

## CHECKLIST 2 — Error Handling Transversal (todos los flows)
Impacto de negocio: si un nodo falla en silencio, el paciente no recibe respuesta y el admin no sabe que falló.

Preguntas:
- [ ] ¿Los nodos HTTP Request tienen "Continue on Fail" o error branch conectado?
- [ ] ¿Qué pasa si la API de Vesalio HCE no responde (timeout / 500)?
- [ ] ¿Qué pasa si PostgreSQL falla durante el agendamiento?
- [ ] ¿Hay nodos críticos sin ningún manejo de error?
- [ ] ¿El paciente recibe algún mensaje cuando algo falla o el chat simplemente muere?

Output requerido:
```
CHECKLIST 2 — Error Handling
¿Fallas silenciosas encontradas?   sí / no — [nodos]
¿API Vesalio HCE sin fallback?     sí / no
¿PostgreSQL sin fallback?          sí / no
¿Paciente recibe mensaje de error? sí / no
Severidad global: CRÍTICO / MEDIO / BAJO
Estimación de fix: __ horas
```

---

## CHECKLIST 3 — Agente Agendar Citas (flujo crítico)
Impacto de negocio: es el core del sistema. Si falla, el paciente no puede agendar.

Preguntas:
- [ ] ¿El Structured Output Parser tiene fallback si el LLM responde en formato incorrecto?
- [ ] ¿Hay validación para fechas ambiguas: "mañana", "el viernes", "en la tarde", "la próxima semana"?
- [ ] ¿La respuesta de confirmación del paciente ("sí", "dale", "ok", "confirmo") está bien cubierta?
- [ ] ¿Hay maxIterations definido en el AI Agent? ¿Cuál es el valor?
- [ ] ¿Puede el agente quedar en loop sin llegar a confirmar el booking?
- [ ] ¿Qué pasa si no hay disponibilidad? ¿El agente ofrece alternativas o se queda sin respuesta?

Output requerido:
```
CHECKLIST 3 — Agente Agendar Citas
¿Output Parser con fallback?      sí / no
¿Fechas ambiguas validadas?       sí / no — ejemplos sin cubrir
¿Confirmación bien cubierta?      sí / no
¿maxIterations definido?          sí / no — valor: __
¿Loop posible sin booking?        sí / no
¿Fallback sin disponibilidad?     sí / no
Severidad global: CRÍTICO / MEDIO / BAJO
Estimación de fix: __ horas
```

---

## CHECKLIST 4 — Routing MIA + Supervisor
Impacto de negocio: si el routing es incorrecto, el paciente que quiere agendar termina en consultas generales y viceversa.

Preguntas:
- [ ] ¿Cómo decide MIA entre "consulta general" vs "agendar cita"? ¿Es un Switch/IF determinístico o lo decide el LLM?
- [ ] ¿Qué hace exactamente el Agente Supervisor? ¿Puede crear un loop con MIA?
- [ ] ¿Hay un caso donde ningún sub-agente se activa y el mensaje queda sin respuesta?
- [ ] ¿El system prompt de MIA tiene instrucciones claras de cuándo usar cada tool?

Output requerido:
```
CHECKLIST 4 — Routing
¿Routing determinístico o LLM?    determinístico / LLM
¿Loop MIA-Supervisor posible?     sí / no
¿Caso sin sub-agente activo?      sí / no
¿System prompt claro en routing?  sí / no
Severidad global: CRÍTICO / MEDIO / BAJO
Estimación de fix: __ horas
```

---

## CHECKLIST 5 — Performance y Costos
Impacto de negocio: llamadas redundantes = costo innecesario + latencia alta = mala experiencia.

Preguntas:
- [ ] ¿Cuántas llamadas a OpenAI hay en un booking completo (happy path)?
- [ ] ¿Hay nodos que llaman a la misma API o DB más de una vez con los mismos parámetros?
- [ ] ¿El Redis TTL está configurado? ¿Puede haber mensajes perdidos por TTL muy corto o duplicados por TTL muy largo?
- [ ] ¿El tamaño del contexto enviado al LLM es razonable o hay datos innecesarios en el prompt?

Output requerido:
```
CHECKLIST 5 — Performance
Llamadas OpenAI por booking:       __ llamadas
¿Llamadas redundantes?             sí / no — [dónde]
¿Redis TTL configurado?            sí / no — valor: __
¿Contexto LLM sobredimensionado?   sí / no
Severidad global: CRÍTICO / MEDIO / BAJO
Estimación de optimización: __ horas
```

---

## CHECKLIST 6 — Seguridad (flag rápido)
Solo identificar si hay problemas obvios. No hace falta análisis profundo.

- [ ] ¿Hay credenciales hardcodeadas en algún nodo (API keys, passwords, tokens)?
- [ ] ¿El webhook de entrada valida el origen (header de WhatsApp/Twilio)?
- [ ] ¿Inputs del usuario van directo a queries SQL sin sanitizar?

Output requerido:
```
CHECKLIST 6 — Seguridad
¿Credenciales hardcodeadas?        sí / no — [nodo]
¿Webhook sin validación de origen? sí / no
¿SQL injection posible?            sí / no
Severidad global: CRÍTICO / MEDIO / BAJO
```

---

## Output final requerido

Al terminar los 6 checklists, genera una tabla resumen:

| Eje | Problema crítico | Severidad | Horas fix |
|---|---|---|---|
| Session State | [sí/no — descripción] | | |
| Error Handling | | | |
| Agente Citas | | | |
| Routing MIA | | | |
| Performance | | | |
| Seguridad | | | |

**Total estimado de horas:**
**Los 2 problemas más urgentes a resolver primero:**
1.
2.
