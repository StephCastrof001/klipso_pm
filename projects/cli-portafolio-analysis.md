# CLI Projects — Análisis de Portafolio PM

> Sesión: 2026-04-05 | Repos: rappi-cli, plaza-vea-cli

---

## Qué son estos proyectos

CLIs en TypeScript que interactúan con APIs privadas de apps de delivery/supermercado (sin SDK oficial), con integración MCP para Claude.

| Repo | Stack | Superficie |
|---|---|---|
| rappi-cli (camilocbarrera) | Bun + Hono + MCP SDK | CLI + REST API + MCP |
| plaza-vea-cli (StephCastrof001) | Node + tsx + MCP SDK | CLI + MCP |

---

## Cómo funciona el flujo de pedido

El LLM NO procesa el pedido. Las llamadas a la API son HTTP directo.
Claude actúa como orquestador — decide qué tools llamar, pero la ejecución es fetch puro.

MCP ≠ LLM: el SDK solo define el protocolo. El "cerebro" vive en Claude externo.

  Tu instrucción
       │
       ├── CLI directa    → comandos manuales
       ├── REST API       → HTTP calls al servidor local (solo rappi-cli)
       └── MCP + Claude   → Claude llama tools en secuencia automática

---

## Señales de seniority PM

### 1. Technical fluency demostrable, no declarativa
Reverse engineering de APIs privadas, auth por cookies, Playwright, servidor MCP con 9-13 tools.
Puedes hablar de orderFormId, centavos vs soles, PATCH vs POST con ingeniería sin explicaciones previas.

### 2. Pensamiento multi-superficie
  CLI → usuario técnico
  REST API → integraciones / scripts  (solo rappi-cli)
  MCP server → Claude como usuario / AI agents

Construir el MCP demuestra que entiendes que el canal es parte del producto. Razonamiento de plataforma, no de feature.

### 3. RESEARCH.md — artefacto de discovery real
Documenta: qué investigaste, qué descubriste que no era obvio, qué no se puede hacer y por qué.
Un PM que escribe así antes de construir reduce retrabajo del equipo de ingeniería.

### 4. analytics + track → pensamiento de retención (Jobs-to-be-Done)
La mayoría construiría solo search y buy.
Identificar que el usuario también quiere entender su gasto y no perderse ofertas es JTBD thinking.

### 5. CONTEXT.md — diseño de interfaz para AI agents
  'cuanto gaste en marzo' -> plaza analytics --month 2025-03
  'busca leche' -> plaza search leche --limit 5
Skill emergente que poca gente en PM tiene documentada.

---

## El proceso seguido (cómo nombrarlo en entrevistas)

| Fase | Lo que hiciste | Equivalente PM |
|---|---|---|
| Discovery / Recon | Interceptar tráfico, mapear endpoints, entender auth | Stakeholder interviews + API audit |
| Constraint mapping | "CVC manual", "MCP no puede hacer login" | Non-negotiables antes de commitear roadmap |
| MVP core | login → search → cart → orders | Flujo mínimo que resuelve el job principal |
| Expansión por Jobs | analytics + track | Features que aumentan valor percibido |
| Multi-surface | MCP server para Claude | Abrir el producto a un nuevo tipo de usuario |
| Handoff docs | CONTEXT.md para agentes AI | Writing specs que el equipo ejecuta sin ti |

---

## Qué pudimos hacer mejor (gaps de PM craft)

### 1. Sin métricas de uso
No hay telemetría. Mejora mínima: log en ~/.plazavea/usage.json con timestamps por comando.

### 2. Sin user research — solo tus propios pain points
¿Cuántos devs más quieren hacer pedidos de supermercado via Claude?
La pregunta faltó antes de construir el MCP (la parte más compleja).

### 3. Funnel MCP incompleto
Claude puede buscar, agregar al carrito, ver resumen — pero no completar el checkout.
Un funnel roto a la mitad es peor que no tener el funnel.
Documentarlo como limitación conocida lo convierte en decisión informada, no en gap.

### 4. Sin onboarding medido
No hay plaza setup ni wizard de first-run. El drop-off en instalación es el mayor problema
de adoption para CLIs.

### 5. CHANGELOG sin historia de decisiones
Un CHANGELOG de PM captura:
- Por qué cookie auth y no OAuth
- Por qué checkout abre browser en vez de ser API-only
- Qué se descartó y por qué
Esas decisiones son el diferenciador en entrevistas.

---

## Oportunidades técnicas clave (para conversar con ingeniería)

| Área | Problema | Por qué importa al PM |
|---|---|---|
| Arquitectura | MCP duplica lógica del core | Mantenimiento doble = velocidad de features a la mitad |
| Performance | Spawna proceso nuevo por cada comando | UX degradado — lentitud visible |
| Feature gap | MCP sin checkout | Job-to-be-done incompleto |
| Alertas de precio | Solo en terminal | Sin notificación = feature inútil si no estás mirando |
| --output json | Inconsistente entre comandos | Bloquea integración con scripts/AI |

---

## Cómo presentarlo en portafolio

NO: "hice un CLI para Plaza Vea"

SÍ:
  "Hice reverse engineering de la API de Plaza Vea, documenté el flujo de auth y checkout,
  identifiqué 3 limitaciones técnicas no evidentes, y diseñé una interfaz CLI + MCP que resuelve
  5 jobs distintos — incluyendo análisis de gasto y alertas de precio.
  El resultado: cualquier AI agent puede operar el supermercado en lenguaje natural."

Artefactos que lo prueban:
  RESEARCH.md   → proceso de discovery documentado
  CONTEXT.md    → diseño de interfaz para AI agents
  Repo público  → shipping real, no solo ideas

---

## Comparativa rappi-cli vs plaza-vea-cli

| Dimensión | rappi-cli | plaza-vea-cli |
|---|---|---|
| Capa de servicios compartida | SÍ (src/services/) | NO — lógica en cada comando |
| REST API propia | SÍ — Hono server | NO — solo CLI |
| Type safety en MCP | SÍ — tipos definidos | NO — any masivo |
| Checkout completo en MCP | SÍ | NO — manual en browser |
| RESEARCH.md | NO | SÍ — muy completo |
| CONTEXT.md para agentes | NO | SÍ — excelente |
| Arquitectura | Más robusta | Más rápida de construir |
