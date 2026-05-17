# Marcos Psicológicos del Aprendizaje
> Base científica de cómo aprende el cerebro humano
> Aplicaciones: aprendizaje personal · diseño de productos · onboarding de usuarios · formación de hábitos

---

## Por qué un PM necesita entender esto

Estos marcos tienen **dos usos simultáneos**:

| Uso | Descripción |
|---|---|
| **Personal** | Aprender cualquier dominio nuevo más rápido: fintech, banca, un nuevo sector, un nuevo stack |
| **De producto** | Diseñar onboardings, tutoriales, canales digitales y flujos de adopción que respetan cómo funciona la memoria |

Un PM que entiende Cognitive Load Theory diseña el onboarding de un canal digital de manera diferente. Un PM que entiende el Efecto de Testing sabe que un wizard con preguntas activas retiene mejor al usuario que un PDF de instrucciones.

---

## NIVEL 1 — Cómo funciona la memoria

### Curva del Olvido — Ebbinghaus (1885)
**El hallazgo:** Sin refuerzo, olvidamos el 70% de lo nuevo en 24 horas.

```
Día 0:   100% ████████████████████
Día 1:    33% ███████
Día 7:    25% █████
Día 30:   15% ███
```

**Uso personal:** El material que estudias una sola vez se olvida. El sistema importa más que el esfuerzo.

**Uso de producto:**
```
Un usuario que completa onboarding el día 1 y no vuelve en 7 días
olvidó el 75% de cómo usar tu producto.
→ Diseño: notificaciones de reactivación en día 3, día 7, día 14
→ Diseño: tooltips contextuales la segunda vez que el usuario abre la app
→ KPI: no medir solo "completó onboarding" — medir "completó segunda operación"
```

**Repo relacionado:** `fsrs4anki/` — implementa el algoritmo que calcula el intervalo óptimo de repaso.

---

### Efecto de Espaciado — Cepeda et al. (Psychological Bulletin, 2006)
**El hallazgo:** Distribuir el estudio en el tiempo produce 2-3x más retención que estudiar el mismo tiempo concentrado (massed practice).

```
Massed practice:  8 horas en 1 día    → retención a 30 días: baja
Spaced practice:  1 hora x 8 días     → retención a 30 días: 2-3x mayor
```

**Uso personal:** Repasar conceptos de un dominio nuevo en intervalos crecientes, no en sesiones maratón.

**Uso de producto:**
```
Un usuario que usa tu canal digital 3 veces en la primera semana
tiene 3x más probabilidad de retención que uno que lo usa 3 veces
el día 1 y no vuelve.
→ Diseño: features que invitan a volver en intervalos (alertas, recordatorios, valor periódico)
→ KPI: frecuencia de uso en primeros 14 días > volumen en día 1
→ Diseño de tutorial: no todo el día 1 — chunk 1 en día 1, chunk 2 en día 3, chunk 3 en día 7
```

**Repo relacionado:** `fsrs4anki/`, `studyield/`

---

### Efecto de Testing (Retrieval Practice) — Roediger & Karpicke (Science, 2006)
**El hallazgo:** Ser EXAMINADO produce +50% más retención que releer el mismo material el mismo tiempo.

```
Grupo A: estudia 4 veces el texto     → 40% retención después de 1 semana
Grupo B: estudia 1 vez + 3 tests      → 65% retención después de 1 semana
```

**Uso personal:** En vez de releer notas, hacerse preguntas. Cerrar el documento y responder desde memoria.

**Uso de producto:**
```
Un onboarding que hace preguntas al usuario ("¿a cuánto equivale tu factura descontada?")
genera más aprendizaje que uno que muestra pantallas informativas.
→ Diseño: wizards con preguntas, no solo slides
→ Diseño: confirmación activa antes del paso crítico ("¿estás seguro de que quieres
   descontar estas 3 facturas por S/45,200?") — no es friction, es encoding
→ Producto educativo: quizzes > videos > lecturas (en ese orden de retención)
```

**Repo relacionado:** `studyield/` — genera quizzes automáticamente del material

---

## NIVEL 2 — Cómo se adquiere expertise

### Práctica Deliberada — Ericsson (Florida State / Harvard)
**El hallazgo:** Los expertos no se distinguen por "horas de práctica" sino por el tipo de práctica. La práctica deliberada tiene 4 condiciones:

```
1. Operar en el EDGE — justo por encima de tu nivel actual
2. Feedback inmediato — saber si lo hiciste bien antes de que pase un día
3. Foco total — 20-30 min de alta concentración > 2 horas distraídas
4. Repetición con variación — mismo concepto, distintos contextos
```

**Uso personal:**
```
❌ Práctica genérica: "practicar entrevistas / leer sobre el dominio"
✅ Práctica deliberada:
   - Grabarse respondiendo → escuchar → identificar el gap exacto
   - Pedir a alguien que interrumpa y pida el número concreto
   - Responder la misma pregunta con distinto caso hasta que fluya
```

**Uso de producto:**
```
Un canal digital que no da feedback inmediato al usuario genera abandono.
→ Diseño: mostrar el monto neto ANTES de confirmar (feedback predictivo)
→ Diseño: notificación de estado en tiempo real, no "te avisamos cuando esté listo"
→ Producto de aprendizaje: el usuario necesita saber si su respuesta fue correcta
   en el mismo momento, no al final del módulo
```

**Repo relacionado:** `nn-zero-to-hero/` (Karpathy: aprender construyendo, no leyendo)

---

### Teoría de Carga Cognitiva — Sweller (UNSW, 1988)
**El hallazgo:** La memoria de trabajo tiene capacidad limitada (~7 elementos simultáneos). Si el material supera esa capacidad, el aprendizaje se bloquea.

**3 tipos de carga cognitiva:**
```
Intrínseca   → dificultad inherente del contenido (reducir con prerequisitos)
Extrínseca   → carga del MAL DISEÑO (eliminar completamente)
Germana      → carga que construye esquemas mentales (maximizar)
```

**Uso personal:**
```
No memorizar respuestas largas — memorizar la ESTRUCTURA (4 bullets) y los NÚMEROS.
El texto fluye desde la estructura, no al revés.
Chunking: estudiar por bloques con un concepto central cada uno.
```

**Uso de producto:**
```
Este es el framework más directo para diseño de UX en canales financieros digitales.

❌ Formulario con 12 campos visibles a la vez → carga extrínseca alta → abandono
✅ Progressive disclosure: 2-3 campos por pantalla → carga manejable → completion

❌ Primera pantalla de Factoring digital muestra: monto, tasa, plazo, TEA, TCEA,
   comisión, mora, garantías, condiciones
✅ Primera pantalla: "¿Cuánto necesitas hoy?" + las facturas disponibles
   El resto aparece cuando el usuario ya tomó la decisión inicial

Regla: si un usuario necesita leer instrucciones para usar tu feature → el diseño falló
```

**Repo relacionado:** `awesome-agi-cocosci/` (sección Cognitive Science cubre literatura de CLT)

---

### Zona de Desarrollo Próximo — Vygotsky
**El hallazgo:** El aprendizaje efectivo ocurre en la zona entre "lo que puedo hacer solo" y "lo que puedo hacer con ayuda."

```
┌─────────────────────────────┐
│  No puedo aunque me ayuden   │ ← demasiado difícil, frustración
└─────────────────────────────┘
┌─────────────────────────────┐
│  Puedo con andamiaje (guía)  │ ← AQUÍ SE APRENDE
└─────────────────────────────┘
┌─────────────────────────────┐
│  Puedo solo, ya lo domino    │ ← zona de confort, no hay crecimiento
└─────────────────────────────┘
```

**Uso personal:** Buscar deliberadamente problemas que estén un nivel por encima de lo que puedes resolver cómodamente. La incomodidad es la señal correcta.

**Uso de producto:**
```
El onboarding de un canal financiero digital opera en ZDP cuando:
→ Le muestra al usuario exactamente el próximo paso (andamiaje)
→ No le muestra todos los pasos a la vez (no lo abruma)
→ Desaparece el andamiaje gradualmente cuando el usuario ya lo domina
   (no seguir mostrando tooltips al usuario experto)

Modelo mental: el ejecutivo de sucursal era el andamiaje humano.
El canal digital necesita reemplazarlo con andamiaje embebido en la UX.
```

---

## NIVEL 3 — Mentalidad y motivación

### Growth Mindset — Dweck (Stanford, Nature)
**El hallazgo:** El fixed mindset interpreta el error como evidencia de falta de capacidad. El growth mindset lo interpreta como información.

**Uso personal:** Los gaps identificados después de un ejercicio no son defectos — son el mapa exacto de qué practicar.

**Uso de producto:**
```
Un canal digital con growth mindset en su diseño:
→ Cuando el usuario falla una validación: "Falta el campo X" (información accionable)
   no "Error: datos inválidos" (juicio sin dirección)
→ Cuando el usuario abandona a la mitad: salva el progreso + invita a continuar
   no reinicia el flujo desde cero (castiga el intento)
```

---

### Self-Determination Theory — Deci & Ryan (Rochester)
**El hallazgo:** La motivación intrínseca (la que dura) requiere tres necesidades:

```
Autonomía   → "Yo elijo hacer esto"
Competencia → "Puedo mejorar, veo progreso"
Relación    → "Esto conecta con algo o alguien que me importa"
```

**Uso personal:** Si el aprendizaje se siente como obligación → revisar cuál de las tres falta.

**Uso de producto:**
```
Autonomía   → el usuario elige qué facturas descontar, no el sistema
Competencia → muestra el progreso: "Ya completaste 3 de 4 pasos"
Relación    → "Tu empresa recibió S/45,200 hoy" (conecta con el resultado real, no con la transacción)

Los productos financieros digitales que fracasan en adopción suelen fallar en Autonomía:
el usuario siente que el sistema lo controla, no que él controla al sistema.
```

---

### Flow — Csikszentmihalyi
**El hallazgo:** El estado de máxima productividad ocurre cuando:
```
Skill ≈ Challenge
```
Challenge >> Skill → ansiedad → abandono
Skill >> Challenge → aburrimiento → desenganche

**Uso de producto:**
```
Un canal financiero digital bien diseñado calibra el challenge según el skill del usuario:
→ Usuario nuevo: pasos guiados, menos opciones visibles, más confirmaciones
→ Usuario experto: shortcuts, acceso directo, menos fricción
→ No mostrar el mismo flujo a ambos (adaptive UX)

KPI relevante: tasa de completitud por cohorte de experiencia
¿Los usuarios nuevos terminan igual que los expertos? Si no → el flujo no adapta el challenge.
```

---

## Resumen aplicado — Para PM de canales digitales

| Framework | Pregunta de diseño que responde |
|---|---|
| Curva del Olvido | ¿Cuándo reactivar al usuario que no volvió? |
| Efecto de Espaciado | ¿Cómo distribuir el onboarding para maximizar retención? |
| Efecto de Testing | ¿Qué tipos de interacción generan más aprendizaje del producto? |
| Práctica Deliberada | ¿Cómo diseñar el feedback para que el usuario mejore cada vez que usa la app? |
| Carga Cognitiva | ¿Cuántos elementos mostrar por pantalla? ¿En qué orden? |
| ZDP | ¿Qué andamiaje necesita el usuario nuevo que el experto ya no necesita? |
| SDT | ¿El usuario siente que controla o que el sistema lo controla? |
| Flow | ¿El nivel de dificultad del flujo coincide con el nivel de experiencia del usuario? |

---

## Repos en esta carpeta y su base científica

| Repo | Base científica | Para qué usarlo |
|---|---|---|
| `fsrs4anki/` | Ebbinghaus + algoritmo FSRS (supera SM-2) | Spaced repetition para aprendizaje personal |
| `studyield/` | Testing effect (Roediger) | Generar quizzes de cualquier material |
| `anki/` | SRS — 28k stars | Herramienta base para memorización de largo plazo |
| `nn-zero-to-hero/` | Deliberate Practice (Karpathy) | Aprender construyendo, no leyendo sobre ello |
| `awesome-agi-cocosci/` | Bayesian learning, developmental psych, CogSci | Literatura científica de cómo aprende el cerebro |
| `awesome-cogsci/` | CogSci books + papers curados | Base teórica de la mente como sistema de aprendizaje |
| `awesome-neuropsychology/` | Neuropsicología + meta-análisis | Cómo el cerebro adquiere habilidades (evidencia empírica) |
| `dopamine/` | Reinforcement learning — mismo mecanismo que reward learning humano | Entender por qué el feedback inmediato funciona |

---

## Paper 2025 más relevante

**Centaur — Nature (2025)**
> Modelo fundacional de cognición humana. Predice comportamiento en cualquier experimento cognitivo.
> Implicación: si puedes modelar el gap cognitivo de tu usuario, puedes diseñar la intervención exacta para cerrarlo.
> Paper: nature.com/articles/s41586-025-09215-4

---

## El insight que resume todo

> El gap entre un usuario que adopta un canal digital y uno que abandona rara vez es el producto.
> Casi siempre es el diseño del aprendizaje embebido en ese producto.
>
> Y el gap entre alguien que aprende un dominio rápido y uno que tarda el doble
> rara vez es inteligencia. Casi siempre es:
> 1. **Calidad del feedback loop** (Ericsson)
> 2. **Espaciado** (Ebbinghaus)
> 3. **Testing, no relectura** (Roediger)
