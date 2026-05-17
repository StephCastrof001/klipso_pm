# Prep Entrevista — PM Factoring & Descuento Electrónico Digital
> Rol: PM que construye canal digital desde cero para Factoring + Descuento Electrónico
> Contexto: migración de canal tradicional (presencial/papel) a canal digital

---

## 1. DOMINIO — Qué debes saber antes de entrar

### ¿Qué es Factoring?
Una empresa tiene facturas por cobrar a 60-90 días. Le vende esas facturas al banco a cambio de liquidez inmediata (menos una comisión). El banco cobra al deudor cuando vence la factura.

```
Empresa A  →  vende factura de S/100k  →  Banco
Banco      →  da S/92k hoy (descuenta 8%)
Banco      →  cobra S/100k en 60 días al deudor
```

### ¿Qué es Descuento Electrónico?
Similar al factoring pero usando facturas electrónicas (SUNAT). La empresa sube su factura electrónica al sistema del banco, el banco la valida contra SUNAT y desembolsa el dinero.

**Diferencia clave:**
- Factoring = puede ser cualquier tipo de documento
- Descuento Electrónico = usa la factura electrónica SUNAT como base → más trazable, más automatizable

### Por qué es un producto PM interesante
El canal tradicional requiere: ir a la sucursal → llevar documentos físicos → esperar evaluación crediticia manual → firma de contratos físicos → esperar desembolso (24-72h).

**El canal digital promete:** subir factura desde app → validación automática contra SUNAT → evaluación crediticia con data → desembolso en horas.

---

## 2. PREGUNTAS TIPO ENTREVISTA — Con respuestas modelo

---

### BLOQUE A: Presentación y Fit

**Q1: Cuéntame sobre ti y por qué te interesa este rol.**

Estructura recomendada (90 segundos):
```
1. Quién soy profesionalmente (15 seg)
2. Qué he hecho relevante para este rol (30 seg)  
3. Por qué este rol específico me interesa (30 seg)
4. Qué aportaré en los primeros 90 días (15 seg)
```

Respuesta modelo:
> "Soy PM con enfoque en productos digitales financieros. He trabajado en [X], donde lideré la migración de [proceso] a canal digital, logrando [resultado medible]. Me interesa este rol porque el Descuento Electrónico en Perú está en un punto de inflexión: las facturas electrónicas SUNAT ya existen, la infraestructura está, pero la experiencia de usuario sigue siendo presencial. Quiero ser quien cierre esa brecha. En los primeros 90 días me enfocaría en hacer discovery profundo con las empresas que usan el canal hoy para entender dónde está la fricción real."

---

**Q2: ¿Qué sabes de Factoring y Descuento Electrónico?**

Respuesta modelo:
> "Factoring es básicamente monetizar cuentas por cobrar antes de su vencimiento — la empresa obtiene liquidez inmediata cediendo el derecho de cobro al banco. Descuento Electrónico es la versión digital-native de eso, usando la factura electrónica de SUNAT como documento base. Lo que me parece interesante del contexto peruano es que ya tienen la infraestructura (SUNAT valida facturas electrónicas en tiempo real), entonces el problema no es técnico — es de experiencia de usuario y de confianza del cliente en el canal digital."

---

### BLOQUE B: Discovery y Customer Journey

**Q3: ¿Cómo harías el discovery para este producto?**

Respuesta modelo (usa JTBD + data):
> "Empezaría por entender el job-to-be-done real. No es 'descontar una factura' — es 'tener liquidez hoy para pagar planilla/proveedor/inventario sin esperar 60 días'. Entonces el discovery tiene dos capas:
> 
> **Cualitativa:** 8-10 entrevistas con clientes actuales del canal presencial. Preguntas clave: ¿cuándo decidiste venir al banco? ¿qué tenías que resolver ese día? ¿qué fue lo más frustrante del proceso? ¿en qué momento dudarías de usar una app para esto?
>
> **Cuantitativa:** Análisis del funnel actual — cuántos inician el proceso, cuántos lo completan, cuánto tiempo tarda cada paso, en qué paso se caen más. Con eso puedo priorizar dónde atacar primero.
>
> También haría shadow sessions: sentarme en la sucursal y ver el proceso en vivo."

---

**Q4: Mapea el customer journey de un cliente que hace Descuento Electrónico hoy (canal tradicional).**

```
CANAL TRADICIONAL HOY:

1. TRIGGER        → Empresa necesita liquidez urgente
2. DECISIÓN       → Decide ir al banco (¿por qué no otra opción?)
3. PREPARACIÓN    → Reúne documentos: facturas, RUC, estados financieros
4. DESPLAZAMIENTO → Va a la sucursal (costo: tiempo, transporte)
5. ESPERA         → Cola en sucursal (20-45 min promedio)
6. ATENCIÓN       → Ejecutivo revisa documentos manualmente
7. EVALUACIÓN     → Área de crédito evalúa (horas o días)
8. APROBACIÓN     → Notificación (puede ser al día siguiente)
9. FIRMA          → Regresa para firmar contrato físico
10. DESEMBOLSO    → 24-72 horas después

FRICCIONES IDENTIFICADAS:
- Paso 3: no saben exactamente qué documentos traer
- Paso 4-5: desplazamiento + espera = costo real para PyME
- Paso 6-7: caja negra — no saben en qué estado está su solicitud
- Paso 9: tienen que regresar solo para firmar
- Paso 10: incertidumbre sobre cuándo llega el dinero
```

**Canal digital que propondrías:**
```
1. TRIGGER        → Misma necesidad urgente de liquidez
2. ACCESO         → App / web → login con credenciales bancarias
3. SELECCIÓN      → Selecciona facturas electrónicas (sync con SUNAT)
4. SIMULACIÓN     → Ve exactamente: monto a recibir, comisión, fecha desembolso
5. CONFIRMACIÓN   → Firma digital (huella/OTP)
6. VALIDACIÓN     → Sistema valida contra SUNAT + score crediticio automático
7. APROBACIÓN     → Notificación push en minutos (no horas)
8. DESEMBOLSO     → En cuenta en 2-4 horas

MEJORAS KPI:
- Tiempo total: 72h → 4h
- Fricciones eliminadas: desplazamiento, espera, caja negra, doble visita
```

---

**Q5: ¿Qué KPIs definirías para medir el éxito del canal digital?**

Respuesta modelo:
```
NORTH STAR METRIC: 
% de operaciones de descuento procesadas en canal digital 
(meta año 1: 30%, año 2: 60%)

ACQUISITION:
- Nuevas empresas activadas en canal digital / mes
- % de clientes actuales que migran al canal digital
- Tasa de abandono en onboarding digital

ACTIVATION:
- % de registrados que completan primera operación
- Tiempo promedio primera operación (target: <15 min)
- Drop-off por paso del funnel

RETENTION:
- % de clientes que repiten operación en 30 días
- Frecuencia promedio de uso / mes

OPERATIONAL:
- Tiempo promedio de aprobación (target: <30 min)
- Tasa de aprobación digital vs presencial
- Tasa de errores en solicitudes digitales

SATISFACTION:
- NPS post-operación (target: >50)
- CSAT en momentos clave (primer desembolso)
```

---

### BLOQUE C: Backlog y Priorización

**Q6: ¿Cómo priorizas el backlog de un producto financiero regulado?**

Respuesta modelo:
> "Uso una matriz de tres dimensiones: valor al cliente, valor al negocio, y factibilidad regulatoria/técnica. En productos financieros el tercer eje es crítico — puedes tener algo muy valioso para el cliente que compliance bloquea por 6 meses. Entonces priorizo:
>
> **Tier 1:** Alta valor + regulatoriamente claro + técnicamente factible → sprint inmediato
> **Tier 2:** Alta valor + requiere validación regulatoria → paralelo con equipo legal
> **Tier 3:** Nice-to-have sin dependencies complejas → backlog, no sprint
>
> Para Factoring específicamente, la primera versión sería solo las 2 funciones que cubren el 80% del volumen: subir factura y ver estado de la solicitud. Todo lo demás es V2."

---

**Q7: Traduce este requerimiento de negocio a historias de usuario:**
*"El área comercial quiere que los clientes puedan hacer descuento de múltiples facturas en una sola operación."*

Respuesta modelo:
```
EPIC: Operación de descuento batch

Historia 1 (MVP):
Como empresa con múltiples facturas pendientes,
Quiero seleccionar varias facturas en una sola sesión,
Para no tener que iniciar el proceso una vez por cada factura.
Criterios de aceptación:
- Puedo seleccionar hasta 10 facturas por operación
- El sistema muestra el monto total neto antes de confirmar
- Una sola firma digital cubre todas las facturas seleccionadas
- Recibo un comprobante consolidado

Historia 2 (V2 — si los datos lo justifican):
Como empresa recurrente,
Quiero configurar reglas automáticas (ej: "descontar todas las facturas >S/10k"),
Para no tener que iniciar sesión cada vez.
(Esta solo se construye si el dato de uso muestra que el 30%+ de clientes repiten la misma selección manual)
```

---

**Q8: ¿Cómo manejas conflictos entre tecnología y negocio?**

Respuesta modelo:
> "Mi rol es ser traductor, no árbitro. Cuando tecnología dice 'eso no se puede en el sprint' y negocio dice 'eso tiene que estar para el lanzamiento', mi trabajo es entender el porqué de ambos lados y buscar el MVP que satisfaga el constraint real.
>
> Ejemplo concreto: si compliance quiere firma manuscrita escaneada para la primera versión y tecnología quiere implementar firma digital (3 meses de desarrollo), propongo un workaround: firma digital básica con OTP para V1, firma avanzada certificada para V2 cuando tengamos el volumen que justifique la inversión. Datos y criterios de decisión sobre la mesa — no opiniones."

---

### BLOQUE D: Ceremonias Ágiles

**Q9: ¿Cómo describes tu rol en cada ceremonia del squad?**

```
DAILY (15 min):
Mi rol: escuchar blockers, no reportar status. 
Si un developer está bloqueado por una definición de negocio → la resuelvo ese día, no mañana.

PLANNING (2-4h):
Mi rol: asegurar que todas las historias tienen criterios de aceptación claros ANTES de entrar al sprint. 
Si una historia llega al planning sin AC → la saco del sprint.

REFINAMIENTO (1-2h):
Mi rol: el más importante para mí. Aquí aclaro dudas, divido historias grandes, y 
aseguro que el equipo entienda el PORQUÉ de cada feature, no solo el QUÉ.

REVIEW (1h):
Mi rol: representar la voz del cliente/negocio. 
Hago preguntas desde el usuario: "¿el cliente entendería este flujo sin explicación?"

RETROSPECTIVA:
Mi rol: participar como un miembro más del equipo, no como "el jefe". 
El equipo habla de proceso, yo hablo de proceso también.
```

---

### BLOQUE E: Preguntas difíciles

**Q10: ¿Cómo medirías si el canal digital está siendo exitoso vs el presencial?**

Respuesta modelo:
> "No es solo volumen — es calidad del volumen. Compararía por cohorte de clientes:
> - **Ticket promedio:** ¿los clientes digitales descontan facturas de mayor o menor monto?
> - **Frecuencia:** ¿vuelven más seguido que los del canal presencial?
> - **Default rate:** ¿el canal digital tiene más o menos defaults? (indica si el modelo de aprobación digital es sólido)
> - **NPS por canal:** ¿el cliente digital está más o menos satisfecho?
> - **Costo por operación:** ¿cuánto cuesta procesar una operación digital vs presencial?
>
> Si el canal digital tiene mejor frecuencia, mismo o menor default, y NPS más alto — es un éxito aunque el ticket sea menor al inicio."

---

**Q11: ¿Qué harías en los primeros 30-60-90 días?**

```
DÍA 1-30: ESCUCHAR
- 10 entrevistas con clientes actuales del canal presencial
- Shadow en sucursal: ver el proceso en vivo
- Reuniones 1:1 con cada área (tecnología, crédito, compliance, comercial)
- Leer todos los tickets/incidencias del sistema actual
- Entender el roadmap existente y los compromisos ya tomados

DÍA 31-60: DIAGNOSTICAR
- Mapear el journey actual completo con métricas reales
- Identificar los 3 dolores más grandes (por frecuencia e impacto)
- Hacer sizing del problema: cuánto volumen, cuánto cuesta hoy
- Proponer el MVP: qué funciones cubren el 80% del caso de uso
- Validar el MVP con 5 clientes antes de escribir una sola historia

DÍA 61-90: CONSTRUIR Y MEDIR
- Primer sprint con el equipo
- Definir los KPIs base (línea de partida)
- Lanzar piloto con 10-20 clientes seleccionados
- Primera review con stakeholders: datos, no promesas
```

---

**Q12: ¿Cómo manejas la resistencia de clientes a migrar al canal digital?**

Respuesta modelo:
> "La resistencia al canal digital en productos financieros tiene dos causas: desconfianza y fricción. Las trato distinto.
>
> Para la **desconfianza**: no intento convencer — demuestro. Piloto con clientes que ya tienen relación de confianza con el banco, muestro los resultados en números (tiempo, costo, seguridad), y dejo que ellos sean los referentes para otros clientes.
>
> Para la **fricción**: la elimino. Si alguien prefiere ir a la sucursal porque el proceso digital es complicado, el problema es mío, no del cliente. El digital tiene que ser más fácil, no solo más rápido."

---

## 3. PREGUNTAS QUE TÚ DEBES HACERLE AL HIRING

Estas preguntas demuestran que piensas como PM senior:

```
1. "¿Cuál es el mayor bloqueador hoy para que este producto esté en digital? 
    ¿Es técnico, regulatorio, o de adopción del cliente?"

2. "¿Tienen data del funnel actual del canal presencial? 
    ¿Saben en qué paso se cae la gente?"

3. "¿El squad de desarrollo ya existe o se forma para este producto?"

4. "¿Cuál es la métrica que el negocio usa hoy para medir el éxito del producto 
    de Factoring? ¿Volumen, margen, NPS?"

5. "¿Qué tan rígidos son los tiempos de compliance para aprobar nuevas 
    funcionalidades digitales? ¿Han hecho esto antes con otros productos?"

6. "¿Cuál sería el primer hito que me diría que estoy teniendo éxito en los 
    primeros 6 meses?"
```

---

## 4. CONTEXTO LATAM PARA HABLAR CON CRITERIO

| Referencia | Qué aprender de ellos |
|---|---|
| **Nubank (Brasil)** | 100% digital desde el inicio, NPS más alto de la industria bancaria |
| **Nequi (Colombia)** | Simulador antes de comprometerse = reduce abandono |
| **Yape (Perú)** | Creció de 4M a 14M con COVID — confianza + simplicidad |
| **Konfío (México)** | Crédito PyME con data alternativa, sin historial crediticio |
| **Mercado Crédito** | Usa historial de transacciones MercadoLibre para scoring |

**El patrón común:** Todos empezaron con UNA funcionalidad muy bien hecha, no con un super-app.

---

## 5. FRAMEWORKS PARA TENER EN LA PUNTA DE LA LENGUA

### CIRCLES (para diseñar productos en la entrevista)
```
C - Comprehend   → ¿Qué problema estamos resolviendo?
I - Identify     → ¿Para quién? (segmento específico)
R - Report needs → ¿Qué necesita ese usuario? (JTBD)
C - Cut          → ¿Qué priorizamos? (no todo)
L - List         → Generar 3 soluciones posibles
E - Evaluate     → Comparar con criterios (velocidad, riesgo, regulación)
S - Summarize    → Recomendar una, explicar por qué
```

### RICE (para priorizar en la entrevista)
```
Reach      × cuántos usuarios afecta
Impact     × qué tan grande es la mejora (1-3-10)
Confidence × qué tan seguro estás (%)
──────────────────────────────────────
Effort     / semanas de desarrollo

Feature con mayor score → primer sprint
```

### STAR (para respuestas comportamentales)
```
S - Situation  → Contexto específico (empresa, momento)
T - Task       → Qué tenías que lograr
A - Action     → Qué hiciste tú específicamente
R - Result     → Resultado medible (número, %)
```

---

## 6. CHECKLIST PRE-ENTREVISTA

```
□ Practica Q1-Q12 en voz alta (no en tu cabeza)
□ Prepara 3 historias STAR con números reales
□ Investiga la empresa específica: ¿tienen app? ¿cómo está su Factoring hoy?
□ Lee sobre factura electrónica SUNAT (sistema OSE/PSE)
□ Estudia el journey de un competitor (BCP, BBVA, Interbank — ¿cómo lo hacen?)
□ Prepara tus 6 preguntas para el hiring manager
□ Ten tu NSM preparado: "el éxito de este producto se mide con X porque..."
□ Practica el customer journey en papel (dibujar el antes/después)
```
