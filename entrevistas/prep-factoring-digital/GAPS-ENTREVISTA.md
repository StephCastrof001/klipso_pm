# Gaps Identificados — Simulación de Entrevista
> Rol: PM Factoring & Descuento Electrónico Digital
> Actualizar a medida que avanza la simulación

---

## P1 — Presentación y Fit

### ✅ Bien
- Números dan credibilidad (10 años, proyectos corporativos e independientes)
- Conexión correcta con el rol: "productos tradicionales con oportunidad de digitalización"
- Mencionó data + customer journey + customer-centric

### ❌ Gaps
1. **Números confusos** — "más de 30 no más de 50... 120... 25" — el hiring manager pierde el hilo. Elegir UN número que impacte.
2. **"Flexiones"** en vez de **"fricciones"** — error verbal recurrente, cuidar en entrevista presencial
3. **No conectó con el dominio** — no mencionó fintech, banca, crédito, facturas. El rol pide conocimiento del mundo financiero
4. **Cierre centrado en ella, no en la empresa** — "estoy buscando mi próximo reto" → cambiar a "quiero aportar en este momento porque..."

### 💡 Frase de cierre mejorada
> "Quiero aportar en este momento específico porque el canal digital de Factoring en Perú todavía está por construirse — y ese es exactamente el tipo de problema en el que he demostrado resultados."

---

## P2 — Discovery desde cero

### ✅ Bien
- Empezar con líderes del canal tradicional → correcto
- Pilotear hipótesis antes de construir → mentalidad PM correcta
- Entrevistas a usuarios + proveedores
- Adopción como métrica de validación

### ❌ Gaps
1. **No nombró as-is/to-be explícitamente** — lo describió pero no usó el vocabulario. En banca ese lenguaje importa
2. **Faltó la capa de data** — el discovery no es solo entrevistas. Antes de hablar con alguien: ¿cuántas ops mensuales? ¿tiempo por paso? ¿tasa de aprobación? ¿monto promedio?
3. **No conectó con el contexto específico** — la factura electrónica SUNAT ya existe y es validable en tiempo real. Eso cambia el diagnóstico del problema
4. **Sin estructura clara** — la respuesta saltó entre ideas sin un framework visible (data → campo → as-is → to-be → validación)

### 💡 Dato clave a mencionar siempre en Factoring/Descuento
> "Las facturas electrónicas SUNAT ya están digitalizadas. El cuello de botella no es el documento — es la evaluación crediticia manual. Ahí es donde atacaría primero."

### 💡 Estructura recomendada para P2
```
1. Data primero    → analizar volumen, tiempos, tasa aprobación del canal actual
2. Campo segundo   → 8-10 entrevistas: clientes, ejecutivos sucursal, equipo crédito
3. Mapear as-is    → proceso completo con fricciones cuantificadas
4. Diseñar to-be   → eliminar fricciones específicas, no agregar features
5. Validar antes   → 5 clientes con prototipo antes del primer sprint
```

---

## P3 — Customer Journey As-Is / To-Be

### ✅ Bien
- Identificó actores correctos: personal humano, cliente, sistema de crédito
- Propuso canal digital con landing + documentos + análisis automatizado
- Mencionó tiempo de desembolso como fricción clave
- Mapear actores para automatizar → thinking correcto

### ❌ Gaps
1. **Sin pasos numerados** — el journey quedó como descripción, no como mapa. Hiring espera: Paso 1... Paso 2... con tiempos reales
2. **"Flexiones"** en vez de "fricciones" — tercer registro. Practicar este término
3. **Fricciones no nombradas específicamente** — no basta decir "hay fricciones", hay que nombrarlas: desplazamiento x2, caja negra, doble visita, evaluación manual
4. **To-be incompleto** — faltó: validación SUNAT automática, firma digital, notificación estado en tiempo real, tiempo esperado (¿de 72h a cuánto?)
5. **"Cuenta nueva"** — error de dominio. En banca regulada no se crean cuentas al vuelo. Correcto: desembolso a cuenta existente del cliente

### 💡 Estructura correcta As-Is
```
Paso 1: Cliente detecta necesidad → reúne docs (1-2 días)
Paso 2: Va a sucursal, hace cola (45-60 min)
Paso 3: Ejecutivo revisa manualmente (30 min)
Paso 4: Evaluación crédito (24-48h — caja negra)
Paso 5: Cliente vuelve a firmar físico (otro desplazamiento)
Paso 6: Desembolso (24-72h)
TOTAL: 3-5 días | FRICCIONES: desplazamiento x2, caja negra, proceso manual
```

### 💡 Estructura correcta To-Be
```
Paso 1: Login app/portal
Paso 2: Sync automático facturas SUNAT
Paso 3: Selecciona facturas → ve monto neto en tiempo real
Paso 4: Score crediticio automático (minutos)
Paso 5: Firma digital con OTP
Paso 6: Desembolso a cuenta existente (2-4h)
TOTAL: menos de 4 horas | FRICCIONES ELIMINADAS: todas las del as-is
```

## Pendientes (simulación en curso)

- [x] P3 — Customer journey as-is / to-be
- [ ] P4 — Cómo decides qué fricciones atacar primero
- [ ] P5 — KPIs para los primeros 6 meses
- [ ] P6 — Trade-off: feature valiosa vs 3 meses de dev
- [ ] P7 — Priorización con stakeholders en conflicto
- [ ] P8 — Rol en ceremonias ágiles
- [ ] P9 — Tecnología dice "no se puede"
- [ ] P10 — Primeros 30-60-90 días
- [ ] P11 — Mayor riesgo del proyecto
- [ ] P12 — Preguntas al hiring manager

---

## Framework Propio — Confirmado y Nombrado

> Estefany tiene un metodología real de transformación de canales. Verbalizarla con vocabulario PM es lo único que falta.

```
Tu framework propio              →  Cómo decirlo en entrevista
──────────────────────────────────────────────────────────────
"Ver la Data del Canal"         →  Baseline Analysis (volumen, tiempos, tasas)
"Entrevistas a usuarios"        →  Discovery cualitativo / field research
"Diagrama As-Is"                →  Customer Journey Map — estado actual
"Identificar fricciones"        →  Pain point mapping con impacto cuantificado
"Armar el To-Be digital"        →  Blueprint del canal objetivo
```

**Pitch en 15 segundos:**
> "Mi punto de partida siempre es el baseline del canal: volumen, tiempos por paso, tasa de éxito. Con eso en la mano, hago 8-10 entrevistas para construir el journey completo. De ahí saco el As-Is con fricciones cuantificadas — y recién diseño el To-Be. No antes."

---

## Patrones recurrentes a trabajar

| Patrón | Frecuencia | Acción |
|---|---|---|
| "Flexiones" en vez de "fricciones" | 2 veces en P1 y P2 | Practicar en voz alta: "fri-ccio-nes" |
| Respuestas sin estructura visible | P1, P2 | Usar siempre un framework: CIRCLES, STAR, o numeración explícita |
| Falta de datos cuantitativos | P2 | Siempre anclar con un número: tiempo, %, costo |
| Cierre débil | P1 | Terminar siempre con impacto para la empresa, no necesidad propia |
