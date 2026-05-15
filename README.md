# klipso_pm — AI Projects for Product Managers

Repositorio de referencia con proyectos de IA construidos por y para PMs. Descargados, analizados y documentados para replicación.

---

## Estructura

```
klipso_pm/
│
├── ai-pm-copilot/              (slgoodrich/agents — ⭐86, 14 forks)
│   ├── plugins/
│   │   ├── ai-pm-copilot/      ← 8 agentes PM especializados
│   │   └── agent-teams/        ← multi-agente: PRD stress test, competitive war room
│   ├── docs/
│   └── README.md
│
├── solo-unicorn/               (pingwu/solo-unicorn — MIT, activo Mayo 2026)
│   ├── skills/                 ← 43 skills: product, marketing, legal, finance, ops
│   │   ├── product/
│   │   ├── idea-validation/
│   │   ├── pm-design-thinking/
│   │   ├── go-to-market/
│   │   ├── growth-analytics/
│   │   ├── career-advisor/
│   │   └── ... (37 más)
│   ├── agents/
│   ├── template_knowledge/
│   ├── template_projects/
│   └── UNICORN_CONSTITUTION.md
│
└── ai-prd-generator/           (cdeust/ai-prd-generator — freemium, Claude Code plugin)
    ├── skills/ai-prd-generator/
    ├── commands/
    ├── mcp-server/
    ├── frameworks/encrypted/   ← parte paga (encriptada en Swift)
    └── examples/               ← PRDs de output real para referencia
```

---

## Proyectos

### 1. AI PM Copilot (`ai-pm-copilot/`)

**Repo original:** [slgoodrich/agents](https://github.com/slgoodrich/agents)

Plugin para Claude Code con 8 agentes PM especializados. Responde preguntas de producto en minutos usando frameworks de Teresa Torres, Marty Cagan, April Dunford.

| Agente | Función |
|---|---|
| `product-manager` | Router principal — delega al especialista correcto |
| `market-analyst` | Análisis competitivo, TAM/SAM/SOM, posicionamiento |
| `research-ops` | Entrevistas de usuario, síntesis, validación |
| `product-strategist` | Visión, OKRs, North Star metric |
| `roadmap-builder` | Now-Next-Later, secuenciación de features |
| `feature-prioritizer` | RICE, ICE, Kano, Value vs Effort |
| `requirements-engineer` | PRDs, user stories, criterios de aceptación |
| `launch-planner` | GTM, beta programs, Product Hunt launch |

**Cómo probar:**
```bash
cd ai-pm-copilot
# En Claude Code:
/plugin install ai-pm-copilot
```

---

### 2. Solo Unicorn Builder (`solo-unicorn/`)

**Repo original:** [pingwu/solo-unicorn](https://github.com/pingwu/solo-unicorn)

Command center de IA para builders que nunca han shippeado algo end-to-end. 43 skills en una sola instalación. Funciona con Claude Code, Gemini CLI, OpenCode.

**Skills PM más relevantes:**
- `product` — Define qué construir y para quién
- `idea-validation` — Presiona el idea antes de buildear
- `pm-design-thinking` — Design thinking aplicado
- `go-to-market` — Estrategia de lanzamiento
- `growth-analytics` — Métricas y crecimiento
- `startup-explorer` — Explora ideas pre-validación

**Cómo probar:**
```bash
cd solo-unicorn
git clone https://github.com/pingwu/solo-unicorn .
# En Claude Code:
# "Run the init unicorn setup"
```

---

### 3. AI PRD Generator (`ai-prd-generator/`)

**Repo original:** [cdeust/ai-prd-generator](https://github.com/cdeust/ai-prd-generator)

Genera PRDs enterprise-grade con un flujo de clarificación interactivo. Output: PRD + JIRA tickets + Test cases + Reporte de verificación.

**Tipos de PRD soportados:** Feature, Bug, Incident, Proposal, MVP, POC, Release, CI/CD

**Modelo:** Freemium — 3 rondas gratis, features avanzadas con licencia de pago.

**Cómo probar (tier gratuito):**
```bash
cd ai-prd-generator
# En Claude Code:
/ai-prd-generator:generate-prd
```

Ver ejemplos de output en `examples/`.

---

## Análisis comparativo

| | ai-pm-copilot | solo-unicorn | ai-prd-generator |
|---|---|---|---|
| **Tipo** | Claude Code plugin | Agent harness multi-CLI | Claude Code plugin |
| **Licencia** | PolyForm Noncommercial | MIT | Freemium |
| **Stars** | ⭐86 | ⭐11 | ⭐4 |
| **Última actividad** | Abril 2026 | Mayo 2026 | Febrero 2026 |
| **Audiencia** | Solo founders / devs | Cualquier builder | PMs y devs |
| **Fortaleza** | Frameworks PM profundos | Amplitud (43 skills) | PRD + JIRA + tests en un flujo |
| **Debilidad** | Solo Claude Code | Complejidad de setup | Parte útil es de pago |

---

## Próximo paso — Proyecto propio

**Idea:** PRD Generator 100% open source + análisis competitivo integrado (via Firecrawl).

```
Input:  "Feature de pagos para app fintech peruana"
Output:
  ├── PRD completo (user stories + criterios de aceptación)
  ├── 3 competidores que ya lo resolvieron (Yape, Culqi, MercadoPago)
  └── Gap analysis — qué puede hacer tú que ellos no hacen
```

**Stack:** Python + Claude API + Firecrawl search. ~200 líneas. 1 día de build.

---

*Research realizado con Firecrawl — Mayo 2026*
