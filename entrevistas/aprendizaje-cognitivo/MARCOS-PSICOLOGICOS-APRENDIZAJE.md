# Marcos Psicológicos del Aprendizaje
> Base científica detrás de los repos en esta carpeta
> Uso: referencia para diseñar sistemas de aprendizaje efectivos (PM skills, dominio financiero, entrevistas)

---

## Por qué importa esto para un PM

Un PM aprende constantemente: nuevos dominios, nuevas empresas, nuevos usuarios.
La diferencia entre ponerse al día en 2 semanas vs 2 meses no es inteligencia —
es si tienes un sistema de aprendizaje basado en cómo funciona realmente la memoria.

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

**Implicación práctica:** No sirve estudiar una vez. El tiempo entre repasos importa más que la cantidad de estudio.

**Repo relacionado:** `fsrs4anki/` — implementa el algoritmo que calcula el intervalo óptimo de repaso.

---

### Efecto de Espaciado — Cepeda et al. (Psychological Bulletin, 2006)
**El hallazgo:** Distribuir el estudio en el tiempo produce entre 2-3x más retención que estudiar el mismo tiempo concentrado.

**Regla de oro:**
```
Intervalo óptimo de repaso = 10-20% del tiempo hasta cuando necesitas recordarlo

Si tienes entrevista en 30 días → repasa cada 3-6 días
Si tienes entrevista en 7 días  → repasa cada 1-2 días
```

**Repo relacionado:** `fsrs4anki/` (algoritmo FSRS supera SM-2 de Anki clásico), `studyield/`

---

### Efecto de Testing — Roediger & Karpicke (Science, 2006)
**El hallazgo:** Ser EXAMINADO produce +50% más retención que releer el mismo material el mismo tiempo.

```
Grupo A: estudia 4 veces el texto     → 40% retención después de 1 semana
Grupo B: estudia 1 vez + 3 tests      → 65% retención después de 1 semana
```

**Implicación práctica:** En vez de releer tus notas de entrevista, hazte preguntas. Cierra el archivo y responde desde memoria.

**Cómo aplicarlo a prep de entrevista:**
```
❌ Releer PREP-ENTREVISTA.md 5 veces
✅ Leer 1 vez → cerrar → responder las 12 preguntas sin ver → revisar gaps
```

**Repo relacionado:** `studyield/` — genera quizzes automáticamente del material

---

## NIVEL 2 — Cómo se adquiere expertise

### Práctica Deliberada — Ericsson (Florida State / Harvard)
**El hallazgo:** Los expertos no se distinguen por "horas de práctica" sino por el tipo de práctica. La práctica deliberada tiene 4 condiciones:

```
1. Operar en el EDGE — justo por encima de tu nivel actual (no fácil, no imposible)
2. Feedback inmediato — sabes si lo hiciste bien antes de que pase un día
3. Foco total — sin distracciones, alta concentración (20-30 min > 2h distraída)
4. Repetición con variación — mismo concepto, distintos contextos
```

**Implicación para prep de entrevista:**
```
❌ Práctica genérica: "releer STAR answers"
✅ Práctica deliberada:
   - Grabarte respondiendo en voz alta (feedback inmediato al escuchar)
   - Que alguien te interrumpa y te pida el número exacto
   - Responder la misma pregunta con distinto caso
   - Cronometrar: ¿puedes dar el RESULT en menos de 20 segundos?
```

**Repo relacionado:** `nn-zero-to-hero/` (Karpathy implementa esto: construir desde cero en vez de leer sobre redes neuronales)

---

### Teoría de Carga Cognitiva — Sweller (UNSW, 1988)
**El hallazgo:** La memoria de trabajo tiene capacidad limitada (7±2 elementos simultáneos). Si el material supera esa capacidad, el aprendizaje se bloquea.

**3 tipos de carga cognitiva:**
```
Intrínseca   → dificultad inherente del material (no se puede reducir mucho)
Extrínseca   → carga que viene del MAL DISEÑO del material (se puede eliminar)
Germana      → carga que va a construir esquemas mentales (la "buena")
```

**Implicación para diseño de recursos de aprendizaje (útil para PM de educación):**
```
❌ Dar toda la info junta: S + T + A + R en un párrafo largo
✅ Chunking: STAR en 4 bloques visuales separados con etiquetas
❌ Jerga sin definir en el primer encuentro
✅ Anclar nuevo concepto en algo conocido antes de agregar complejidad
```

**Implicación para prep de entrevista:**
```
No memorices respuestas largas — memoriza la ESTRUCTURA (4 bullets) y los NÚMEROS.
El texto fluye desde la estructura, no al revés.
```

**Repo relacionado:** `awesome-agi-cocosci/` (sección de Cognitive Science cubre literatura de CLT)

---

### Zona de Desarrollo Próximo — Vygotsky
**El hallazgo:** El aprendizaje efectivo ocurre en la zona entre "lo que puedo hacer solo" y "lo que puedo hacer con ayuda."

```
                    ┌─────────────────────────────┐
                    │  No puedo aunque me ayuden   │ ← Demasiado difícil
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
     ZONA DE        │  Puedo con ayuda / andamiaje │ ← AQUÍ SE APRENDE
   DESARROLLO  →    └─────────────────────────────┘
     PRÓXIMO        ┌─────────────────────────────┐
                    │  Puedo solo, ya lo domino    │ ← Zona de confort (no crece)
                    └─────────────────────────────┘
```

**Implicación práctica:**
Simular entrevista con alguien que te interrumpe, te pide números, te desafía — eso es andamiaje. Es incómodo y es exactamente por eso que funciona.

---

## NIVEL 3 — Mentalidad y motivación

### Growth Mindset — Dweck (Stanford, publicado en Nature)
**El hallazgo:** Las personas con fixed mindset evitan el error porque lo interpretan como "no soy bueno en esto." Las personas con growth mindset interpretan el error como información.

**El cambio concreto:**
```
Fixed mindset:  "Cometí errores en P1-P3 → no soy buena en entrevistas"
Growth mindset: "Cometí errores en P1-P3 → sé exactamente qué practicar"
```

**Implicación directa:** El GAPS-ENTREVISTA.md no es una lista de defectos. Es un mapa de práctica deliberada.

---

### Self-Determination Theory — Deci & Ryan (Rochester)
**El hallazgo:** La motivación intrínseca (la que dura) viene de tres necesidades:
```
Autonomía   → "Yo elijo hacer esto"
Competencia → "Puedo mejorar con esfuerzo"
Relación    → "Esto conecta con personas o causas que me importan"
```

**Implicación:** Si la prep de entrevista se siente como tortura → falta alguna de las tres.

---

### Flow — Csikszentmihalyi
**El hallazgo:** El estado de máxima productividad (flow) ocurre cuando:
```
Skill ≈ Challenge
```
Si el challenge supera el skill → ansiedad → bloqueo
Si el skill supera el challenge → aburrimiento → distracción

**Para prep de entrevista:**
Si una pregunta te genera ansiedad → divídela en partes más pequeñas
Si una pregunta te parece trivial → súbele el nivel: pide feedback en voz alta, cronometra, agrega un número real

---

## Ruta práctica — De la ciencia a la práctica

### Para prep de entrevista PM (aplicación inmediata)

```
DÍA 1-3:   Lee el material una vez (PREP-ENTREVISTA.md, casos_star_pm_steph.md)
            → No releer. Solo una lectura activa.

DIARIO:     20 min de práctica deliberada en el EDGE
            → Grábate respondiendo 1 pregunta. Escúchate. Nota el gap.
            → No "repasar" — RESPONDER sin ver las notas

ESPACIADO:  Usa tarjetas o un sistema para repasar los números clave:
            "3 meses → 3 ciudades → S/3M" / "S/60M con gastos acotados"
            → Los números anclan la historia en la memoria

FEEDBACK:   Simula entrevista con alguien real o grábate en video
            → Escuchar tu propia voz diciendo "flexiones" en vez de "fricciones"
               es el feedback más efectivo que puede haber
```

### Para aprender un dominio nuevo rápido (ej: Factoring, fintech)

```
Semana 1:   Lectura superficial → construir mapa mental del dominio
            (awesome-agi-cocosci sección Cognitive Science para base)

Semana 2+:  Anki/FSRS con los conceptos clave del dominio
            → No definiciones largas. Tarjetas de una pregunta / una respuesta.

Diario:     Deliberate practice → aplicar el concepto a un caso nuevo cada día
            → "¿Cómo afecta la Teoría de Carga Cognitiva al diseño del onboarding digital?"

Mensual:    Retrieval test → responde sin ver las notas, luego revisa
```

---

## Repos en esta carpeta y su base científica

| Repo | Base científica | Para qué usarlo |
|---|---|---|
| `fsrs4anki/` | Ebbinghaus + algoritmo FSRS (mejor que SM-2) | Spaced repetition para conceptos de dominio |
| `studyield/` | SRS + AI quiz (testing effect, Roediger) | Generar quizzes automáticos de tu material |
| `anki/` | Spaced Repetition System — 28k stars | Herramienta base para memorización de largo plazo |
| `nn-zero-to-hero/` | Deliberate Practice (Karpathy) | Aprender construyendo, no leyendo sobre ello |
| `awesome-agi-cocosci/` | Bayesian learning, developmental psych, CogSci | Literatura científica de cómo aprende el cerebro |
| `awesome-cogsci/` | CogSci books + papers curados | Base teórica de la mente como sistema de aprendizaje |
| `awesome-neuropsychology/` | Neuropsicología + meta-análisis | Cómo el cerebro adquiere habilidades (evidencia empírica) |
| `dopamine/` | Reinforcement learning (mismo mecanismo que reward learning humano) | Entender por qué el feedback inmediato funciona |

---

## Paper + Repo más relevante 2025

**Centaur — Nature 2025**
> Modelo fundacional de cognición humana que predice comportamiento en cualquier experimento cognitivo.
> Implicación práctica: si puedes modelar tu propio gap cognitivo, puedes cerrarlo más rápido.
> Paper: nature.com/articles/s41586-025-09215-4

---

## El insight que resume todo

> El gap entre alguien promedio y alguien "top" rara vez es talento.
> Casi siempre es:
> 1. **Calidad del loop de feedback** (Ericsson) — ¿sé inmediatamente si lo hice bien?
> 2. **Espaciado** (Ebbinghaus) — ¿estoy repasando en el momento óptimo?
> 3. **Testing effect** (Roediger) — ¿me estoy examinando o solo releyendo?
>
> Los tres están implementados en Anki/FSRS y documentados en awesome-agi-cocosci.
