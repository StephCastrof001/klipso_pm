# Prep Entrevista — PM Factoring & Descuento Electrónico Digital
> Rol: PM que construye canal digital desde cero para Factoring + Descuento Electrónico
> Contexto: migración de canal tradicional (presencial/papel) a canal digital
> Todas las respuestas modelo usan estructura STAR

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

## 2. PREGUNTAS TIPO ENTREVISTA — Con respuestas modelo en STAR

> **Estructura STAR:**
> - **S — Situation:** contexto específico (empresa, momento, escala)
> - **T — Task:** qué tenías/tendrías que lograr
> - **A — Action:** qué hiciste/harías tú específicamente (pasos concretos)
> - **R — Result:** resultado medible (número, tiempo, %)

---

### BLOQUE A: Presentación y Fit

---

**Q1: Cuéntame sobre ti y por qué te interesa este rol.**

*(Comportamental — usa STAR con experiencia real)*

```
STAR APLICADO A Q1:

S — "Llevo 10 años trabajando en productos digitales, con foco en los últimos 5 
     en canales de atención. Mi contexto más reciente fue [empresa], un producto 
     que atendía a [segmento] con un proceso 100% presencial."

T — "Mi tarea fue reducir el costo por atención y aumentar la adopción digital 
     sin perder la tasa de resolución que tenía el canal físico."

A — "Lo que hice fue: primero mapeé el canal existente con data y entrevistas 
     para entender dónde estaban las fricciones reales. Luego diseñé el canal 
     digital en capas — empezando por las operaciones de mayor volumen — y lo 
     validé con usuarios antes del primer sprint."

R — "Logramos [X% de adopción digital / reducción de tiempo de X a Y / NPS 
     de Z] en los primeros [N] meses."
```

**Cierre — siempre terminar con valor para la empresa, no necesidad propia:**
> *"Me interesa este rol porque el Descuento Electrónico en Perú tiene la infraestructura lista — las facturas SUNAT ya son electrónicas — pero la experiencia sigue siendo presencial. Quiero aportar en este momento específico porque es exactamente el tipo de transición en la que he demostrado resultados."*

---

**Q2: ¿Qué sabes de Factoring y Descuento Electrónico?**

*(Domain knowledge — adapta STAR con contexto de aprendizaje)*

```
S — "Cuando empecé a explorar este rol, investigué el estado del producto 
     en el mercado peruano."

T — "Necesitaba entender no solo el producto financiero, sino dónde está 
     la oportunidad de digitalización."

A — "Lo que encontré es que Factoring es básicamente monetizar cuentas por 
     cobrar antes de su vencimiento — la empresa obtiene liquidez cediendo 
     el derecho de cobro al banco. Descuento Electrónico es la versión 
     digital-native, usando la factura electrónica SUNAT como base.

     Lo clave del contexto peruano: SUNAT ya valida facturas en tiempo real. 
     Entonces el cuello de botella no es el documento — es la evaluación 
     crediticia manual y la experiencia de usuario en el canal."

R — "Eso me dice que el problema es de producto y adopción, no técnico. 
     La infraestructura ya existe. Falta el canal."
```

---

### BLOQUE B: Discovery y Customer Journey

---

**Q3: ¿Cómo harías el discovery para este producto?**

*(Situacional — STAR como 'así lo haría')*

```
S — "Me enfrento a un canal que no conozco directamente: Factoring presencial, 
     con clientes PyME que confían en el ejecutivo de sucursal."

T — "Mi tarea es entender el canal actual antes de diseñar el digital. 
     No puedo proponer un To-Be sin entender el As-Is."

A — "Mi punto de partida siempre es la data del canal:
     - ¿Cuántas operaciones mensuales? ¿Qué monto promedio?
     - ¿Cuánto tarda cada paso? ¿En qué paso se cae la gente?
     - ¿Cuál es la tasa de aprobación actual?
     Con ese baseline en la mano, hago 8-10 entrevistas: 
     clientes actuales, ejecutivos de sucursal, equipo de crédito.
     La pregunta clave no es '¿usarías una app?' — es '¿cuándo necesitaste 
     liquidez urgente y qué fue lo más frustrante del proceso?'
     Luego mapeo el As-Is con fricciones cuantificadas (tiempo, costo, 
     frecuencia de queja) y recién diseño el To-Be."

R — "El resultado esperado: antes del primer sprint tengo 3 fricciones 
     priorizadas por impacto y validadas con al menos 5 clientes."
```

---

**Q4: Mapea el customer journey de un cliente que hace Descuento Electrónico hoy.**

*(Técnico — STAR como estructura de presentación)*

```
S — "El canal actual es 100% presencial. El cliente es una PyME que necesita 
     liquidez antes del vencimiento de sus facturas."

T — "Mi trabajo es documentar cada paso, con tiempos y fricciones, para 
     identificar dónde atacar primero."

A — "El As-Is tiene 6 pasos con fricciones concretas:

     Paso 1: Cliente detecta necesidad de liquidez → reúne documentos (1-2 días)
             FRICCIÓN: no sabe exactamente qué traer
     Paso 2: Va a sucursal → hace cola (45-60 min)
             FRICCIÓN: desplazamiento + espera = costo real para la PyME
     Paso 3: Ejecutivo revisa documentos manualmente (30 min)
             FRICCIÓN: proceso manual, depende de la persona
     Paso 4: Evaluación crediticia (24-48h — caja negra)
             FRICCIÓN: cliente no sabe qué pasa con su solicitud
     Paso 5: Cliente vuelve a firmar físico (segundo desplazamiento)
             FRICCIÓN: viaje solo para una firma
     Paso 6: Desembolso a cuenta (24-72h)
             FRICCIÓN: incertidumbre sobre cuándo llega el dinero
     TOTAL: 3-5 días

     El To-Be elimina todas esas fricciones:

     Paso 1: Login app/portal
     Paso 2: Sync automático con SUNAT → facturas cargadas sin subir nada
     Paso 3: Selecciona facturas → ve monto neto y comisión en tiempo real
     Paso 4: Score crediticio automático (minutos, no horas)
     Paso 5: Firma digital con OTP
     Paso 6: Desembolso a cuenta existente del cliente (2-4 horas)
     TOTAL: menos de 4 horas"

R — "Resultado esperado: tiempo de 3-5 días a menos de 4 horas. 
     Fricciones eliminadas: desplazamiento x2, caja negra, proceso manual, 
     incertidumbre de desembolso."
```

---

**Q5: ¿Qué KPIs definirías para medir el éxito del canal digital?**

*(Situacional + Comportamental — la North Star cambia según la etapa del producto)*

```
S — "En Ágora pasamos por dos momentos distintos que requirieron 
     North Stars distintas. Usar la misma métrica en un canal nuevo 
     que en uno que reemplaza a un canal tradicional es un error."

T — "La métrica correcta depende de la etapa de madurez del producto, 
     no de una lista genérica de KPIs."

A — "Estructuro en dos etapas y aplico la regla 5-3-1:
     1 North Star → 3 inputs que la mueven → 5 métricas operacionales

     ETAPA 1 — Canal nuevo (0 a 1):
     North Star: Usuarios activos mensuales
     → ¿La gente usa el canal siquiera?
     Inputs: % que completa primera operación | FCR | tiempo hasta primera op

     ETAPA 2 — Reemplazando canal tradicional:
     North Star: Tasa de adopción digital
     → % de operaciones procesadas en canal digital vs total
       (meta mes 3: 15% | mes 6: 30%)

     3 inputs que mueven la North Star:
     1. Activation rate — % registrados que completan primera operación
        (target: >40% en 14 días — leading indicator de retención)
     2. D30 Retention — % que repite operación en primeros 30 días
        (target: >20%)
     3. SLA digital — % de operaciones aprobadas en <30 min
        (vs 24-48h del canal presencial — mide si el canal funciona)

     5 métricas operacionales por etapa AARRR:
     Acquisition : % clientes del canal presencial que se registran
     Activation  : Time to First Value — tiempo hasta primera op (<15 min)
     Retention   : Drop-off por paso del funnel (dónde abandona la gente)
     Revenue     : ROI canal digital vs presencial — costo op + default rate
     Referral    : NPS post-operación (target >50)

     FCR — First Contact Resolution:
     Si el usuario resolvió sin contactar soporte ni ir a sucursal.
     FCR alto = el diseño funciona solo.
     FCR bajo = el onboarding tiene fricciones no resueltas."

R — "El ROI del canal fue clave porque nos permitió visibilizar si las 
     acciones que tomábamos eran las correctas. Cumplimos los tiempos 
     acordados y superamos los objetivos en un 30% sobre lo planificado."
```

**Métricas vanidad a evitar:**
```
❌ Total usuarios registrados → siempre sube aunque nadie opere
❌ Número de logins          → no indica si resolvió su necesidad
❌ Descargas de la app       → no predice retención ni revenue
✅ Activation rate, D30 Retention, FCR, SLA digital, ROI por canal
```

---

### BLOQUE C: Backlog, Priorización y Trade-offs

---

**Q6: Tecnología dice que la feature más valiosa toma 3 meses. El negocio quiere lanzar en 6 semanas. ¿Qué haces?**

*(Comportamental — trade-off scope vs tiempo)*

```
S — "Tecnología me dice que la feature más valiosa — firma digital 
     biométrica — toma 3 meses. El negocio quiere lanzar en 6 semanas."

T — "Mi trabajo no es elegir un bando — es encontrar el scope mínimo 
     que cumpla el objetivo de negocio en el tiempo disponible."

A — "Tres pasos:
     1. Voy con el negocio primero: ¿qué es lo MÍNIMO que tiene que 
        salir en 6 semanas para que el lanzamiento tenga valor?
     2. Con ese scope reducido vuelvo a tecnología: ¿cuánto toma esto?
     3. Si hay gap, busco con ambos qué parte puede ser manual o 
        semi-automatizada temporalmente — no todo tiene que ser 
        automático en V1.
     Convoco mesa conjunta: pongo las opciones sobre la tabla.
     Qué sale en 6 semanas. Qué va a V2. Qué puede hacerse 
     manualmente mientras tanto. Cada área ve el trade-off completo."

R — "Lanzamos con el scope mínimo viable en fecha.
     El negocio cumplió su objetivo. Tecnología entregó sin deuda técnica.
     La parte manual se automatizó en el siguiente ciclo."
```

---

**Q7: El área comercial quiere más features para atraer clientes. El área de crédito quiere reforzar controles de riesgo antes de crecer. Eres la PM. ¿Cómo lo resuelves?**

*(Comportamental — stakeholders en conflicto con historia real)*

```
S — "En Ágora teníamos cuatro áreas compitiendo por el mismo backlog: 
     operaciones, negocio, comercial y marketing. 
     Todos con requerimientos urgentes, todos con razones válidas."

T — "Tenía que priorizar sin perder la confianza de ningún área 
     y sin que el equipo técnico estuviera bloqueado."

A — "Establecí dependencias entre requerimientos:
     Primero identifiqué cuáles eran CRÍTICOS — impacto en usuarios 
     activos o riesgo de negocio — y cuáles eran COMPLEMENTARIOS.
     Con esa clasificación hablé con cada área:
     'Este requerimiento entra primero porque afecta X usuarios o 
     bloquea Y proceso. El tuyo entra en el siguiente ciclo porque 
     agrega valor pero no bloquea nada hoy.'
     
     Para el caso comercial vs crédito específicamente:
     Cuantifico el esfuerzo y riesgo de cada iniciativa.
     Si reforzar controles toma 2 meses y la feature comercial 6 meses,
     el orden se decide por datos, no por jerarquía.
     Busco también el mínimo viable de cada lado:
     ¿Puede comercial salir con una feature puntual más pequeña?
     ¿Puede crédito reforzar los controles más críticos primero?
     La clave: cada área entiende el criterio, no solo la decisión."

R — "Resolvimos muchas contingencias sin escalar.
     Cumplimos todas las entregas planificadas 
     y superamos los objetivos en un 20%."
```

---

**Q8: ¿Cómo priorizas el backlog de un producto financiero regulado?**

*(Comportamental — usa STAR con experiencia real o caso concreto)*

```
S — "En productos financieros hay un eje adicional que no existe en otros 
     productos: la factibilidad regulatoria. Algo puede ser muy valioso 
     para el cliente y estar bloqueado 6 meses por compliance."

T — "Mi tarea es priorizar sin ignorar ese eje."

A — "Uso una matriz de tres dimensiones:
     1. Valor al cliente (impacto en journey y frecuencia de uso)
     2. Valor al negocio (volumen de operaciones, margen, adopción)
     3. Factibilidad (regulatoria + técnica + tiempo de entrega)

     Tier 1: alto valor + regulatoriamente claro + factible → sprint inmediato
     Tier 2: alto valor + requiere validación regulatoria → corro en paralelo 
             con legal mientras el equipo trabaja en Tier 1
     Tier 3: nice-to-have sin dependencies críticas → backlog, no sprint

     Para el MVP de Factoring específicamente: solo dos funciones cubren 
     el 80% del caso de uso — subir factura y ver estado de la solicitud. 
     Todo lo demás es V2."

R — "El resultado de esta priorización es un roadmap que el negocio entiende, 
     legal puede anticipar, y tecnología puede ejecutar sin bloqueos constantes."
```

---

**Q7: Traduce este requerimiento a historias de usuario:**
*"El área comercial quiere que los clientes puedan descontar múltiples facturas en una sola operación."*

*(Técnico — STAR como proceso de traducción)*

```
S — "El requerimiento viene del área comercial en lenguaje de negocio, 
     no en lenguaje de usuario."

T — "Necesito convertirlo en historias que el equipo pueda ejecutar, 
     con criterios de aceptación verificables."

A — "Primero valido si el problema existe: ¿cuántos clientes hoy hacen 
     múltiples operaciones separadas? Si el dato lo confirma, escribo:

     HISTORIA MVP:
     Como empresa con múltiples facturas pendientes,
     Quiero seleccionar varias en una sola sesión,
     Para no iniciar el proceso una vez por cada factura.
     
     Criterios de aceptación:
     - Selecciono hasta 10 facturas por operación
     - Veo el monto total neto antes de confirmar
     - Una firma digital cubre todas las facturas seleccionadas
     - Recibo un comprobante consolidado

     HISTORIA V2 (solo si el dato lo justifica):
     Como empresa recurrente,
     Quiero configurar reglas automáticas de descuento,
     Para no iniciar sesión cada vez.
     → Esta historia entra al roadmap SOLO si el 30%+ de clientes 
       repiten la misma selección manual."

R — "El equipo puede estimar, implementar y verificar. 
     El negocio puede ver exactamente qué se construye y cuándo."
```

---

**Q8: ¿Cómo manejas conflictos entre tecnología y negocio?**

*(Comportamental — usa STAR con ejemplo concreto)*

```
S — "En el lanzamiento de [producto/feature], compliance exigía firma 
     manuscrita escaneada. Tecnología había diseñado firma digital OTP. 
     Ambos equipos tenían razón dentro de su dominio."

T — "Mi trabajo era desbloquearlo sin sacrificar ni el cumplimiento 
     regulatorio ni el tiempo de lanzamiento."

A — "Lo que hice fue: entender el porqué real de cada posición.
     Compliance no quería firma manuscrita per se — quería trazabilidad 
     y no-repudio del contrato. Tecnología podía entregar eso con OTP en V1 
     y firma avanzada certificada en V2.
     Propuse ese camino con criterios de decisión sobre la mesa: 
     OTP cumple el requisito de trazabilidad en el rango de montos del MVP. 
     Firma avanzada se agrega cuando el volumen justifique la inversión.
     Ambos equipos lo aceptaron porque la decisión se basó en datos, 
     no en jerarquía."

R — "Lanzamos en fecha con firma OTP. 
     V2 con firma avanzada se planificó para el trimestre siguiente."
```

---

### BLOQUE D: Ceremonias Ágiles

---

**Q9: ¿Cómo describes tu rol en cada ceremonia del squad?**

*(Situacional — STAR adaptado como 'así es mi estilo')*

```
S — "Trabajo con squads donde el PM puede convertirse en el cuello 
     de botella si no está disponible en el momento correcto."

T — "Mi trabajo en cada ceremonia es específico y distinto."

A — "Así lo aplico:

     DAILY (15 min):
     Mi rol: escuchar blockers, no reportar status.
     Si un developer está bloqueado por una definición → la resuelvo ese día.

     PLANNING (2-4h):
     Mi rol: asegurarme de que CADA historia tenga criterios de aceptación 
     claros ANTES de entrar al sprint. Si una historia no tiene AC → la saco.

     REFINAMIENTO (1-2h):
     Mi rol más importante. Aquí aclaro el PORQUÉ de cada feature, no solo 
     el QUÉ. El equipo que entiende el porqué toma mejores micro-decisiones.

     REVIEW (1h):
     Mi rol: representar la voz del cliente. 
     Pregunta que hago siempre: '¿el cliente entendería esto sin explicación?'

     RETROSPECTIVA:
     Mi rol: participar como miembro del equipo, no como jefe. 
     Hablo de proceso, no de personas."

R — "El resultado es un squad que no está esperando respuestas del PM 
     para avanzar, porque las preguntas se resolvieron antes del sprint."
```

---

---

**Q10: Estás en el sprint day 5. El área comercial llega con un requerimiento urgente. ¿Qué haces?**

*(Comportamental — gestión de sprint bajo presión)*

```
S — "En Ágora era frecuente que llegaran requerimientos urgentes 
     en medio del sprint — desde comercial, operaciones, negocio."

T — "Mi regla es no modificar el sprint una vez que inicia.
     Pero hay excepciones — y necesito un criterio claro."

A — "Aplico un test de dos condiciones:
     1. ¿El requerimiento afecta a usuarios activos HOY?
     2. ¿El costo de no hacerlo supera el costo de romper el sprint?
     
     Si ambas respuestas son SÍ → es crítico, entra al sprint.
        Comunico inmediatamente a todos los stakeholders qué quedó 
        de lado y por qué. No como sorpresa al final — en el momento.
     
     Si alguna respuesta es NO → va al backlog.
        Entra al siguiente planning con toda la información.
        El área que lo pidió recibe una fecha concreta, no un 'veremos'."

R — "El equipo mantuvo cadencia de sprints estable.
     Los stakeholders confiaban en el proceso porque entendían 
     los criterios — sus requerimientos no se ignoraban, 
     se gestionaban con lógica y transparencia."
```

---

### BLOQUE E: Preguntas difíciles

---

**Q11: En medio del sprint, el tech lead te dice que la integración con SUNAT toma el doble de lo estimado. ¿Cómo reaccionas?**

*(Situacional — blocker técnico inesperado)*

```
S — "Estamos en sprint. La integración con SUNAT — que valida las 
     facturas electrónicas en tiempo real — era el corazón del MVP.
     El tech lead dice que toma el doble."

T — "Necesito desbloquearlo sin cancelar el sprint ni perder la fecha 
     de lanzamiento con los clientes piloto."

A — "Primero entiendo el por qué: ¿es un problema de estimación,
     de documentación de la API de SUNAT, o de un blocker nuevo?
     
     Con esa información evalúo tres opciones:
     Opción 1 — Workaround manual: el ejecutivo valida la factura 
                contra SUNAT manualmente para el piloto. 
                Se automatiza en V2.
     Opción 2 — Scope reducido: lanzar sin validación SUNAT en V1,
                con validación manual como gate. 
                Riesgo controlado para piloto pequeño.
     Opción 3 — Extender el sprint: solo si el impacto al cliente
                de no tener SUNAT es bloqueante para el piloto.
     
     Comunico a los stakeholders el trade-off antes de decidir:
     no los sorprendo con un retraso — los involucro en la decisión."

R — "El piloto lanzó en fecha con workaround manual.
     La integración SUNAT automática entró en el siguiente sprint.
     Los 10 clientes piloto completaron operaciones sin fricciones."
```

---

**Q12: ¿Cuál es el mayor riesgo de este proyecto y cómo lo mitigarías?**

*(Estratégico — visión de riesgo PM)*

```
S — "Estamos construyendo un canal digital para un producto financiero 
     regulado, con clientes PyME que confían en el ejecutivo humano."

T — "Necesito identificar el riesgo que puede matar el proyecto — 
     no el más técnico, sino el más real."

A — "El mayor riesgo no es técnico — es de adopción.
     Puedes construir el mejor canal digital del mercado y que nadie 
     lo use porque los clientes siguen llamando al ejecutivo.
     
     Lo mitigo en tres frentes:
     1. PILOTO con clientes de alto NPS: empiezo con los que ya 
        confían en el banco, no con los escépticos. 
        Ellos se convierten en referentes.
     2. DISEÑO que no asume conocimiento: si el usuario necesita 
        leer instrucciones, el diseño falló. FCR es el guardrail.
     3. EJECUTIVO como aliado, no como enemigo: el canal digital 
        no elimina al ejecutivo en V1 — lo libera de tareas repetitivas 
        para que se enfoque en clientes con necesidades complejas."

R — "El riesgo de adopción se mitiga antes del lanzamiento, 
     no después. Si en el piloto el 40% completa la primera operación 
     solo, el canal es viable. Si no llega a ese threshold, 
     hay que rediseñar antes de escalar."
```

---

**Q13: ¿Qué medirías para comparar canal digital vs canal presencial?**

*(Analítico — STAR como metodología de análisis)*

```
S — "Tenemos dos canales corriendo en paralelo: presencial y digital. 
     El negocio quiere saber si el canal digital está funcionando."

T — "No basta con mirar volumen — necesito medir calidad del volumen."

A — "Comparo por cohorte de clientes, no por canal en abstracto:
     - Ticket promedio: ¿los clientes digitales descuentan facturas 
       de mayor o menor monto?
     - Frecuencia: ¿vuelven más seguido que los del canal presencial?
     - Default rate: ¿el canal digital tiene más o menos defaults?
       (esto indica si el modelo de aprobación digital es sólido)
     - NPS por canal: ¿el cliente digital está más o menos satisfecho?
     - Costo por operación: ¿cuánto cuesta procesar digital vs presencial?"

R — "Si el canal digital tiene mejor frecuencia, mismo o menor default, 
     y NPS más alto — es un éxito aunque el ticket sea menor al inicio. 
     Eso me dice que estamos captando un segmento nuevo, no canibalizando 
     el canal existente."
```

---

**Q11: ¿Qué harías en los primeros 30-60-90 días?**

*(Situacional — STAR como plan de acción)*

```
S — "Llego a un producto que existe en canal presencial pero no tiene 
     canal digital. Hay una organización con equipos formados, compromisos 
     ya tomados, y una cultura que no conozco."

T — "En 90 días necesito entender el problema real, alinear a los 
     stakeholders, y lanzar algo que demuestre tracción."

A — "Lo estructuro en tres fases:

     DÍA 1-30: ESCUCHAR
     - 10 entrevistas con clientes actuales del canal presencial
     - Shadow en sucursal: ver el proceso en vivo
     - Reuniones 1:1 con cada área (tech, crédito, compliance, comercial)
     - Leer todos los tickets/incidencias del sistema actual
     - Entender el roadmap existente y los compromisos ya tomados

     DÍA 31-60: DIAGNOSTICAR
     - Mapear el journey actual completo con métricas reales
     - Identificar las 3 fricciones de mayor impacto (por frecuencia y costo)
     - Hacer sizing: cuánto volumen, cuánto cuesta hoy, cuánto puede mejorar
     - Proponer el MVP: qué funciones cubren el 80% del caso de uso
     - Validar el MVP con 5 clientes antes de escribir una sola historia

     DÍA 61-90: CONSTRUIR Y MEDIR
     - Primer sprint con el equipo
     - Definir la línea de base de los KPIs
     - Lanzar piloto con 10-20 clientes seleccionados
     - Primera review con stakeholders: datos, no promesas"

R — "Al día 90 tengo: un canal digital en manos de clientes reales, 
     métricas base establecidas, y la primera señal de si el approach 
     es correcto o necesita ajuste."
```

---

**Q12: ¿Cómo manejas la resistencia de clientes a migrar al canal digital?**

*(Comportamental — usa STAR con experiencia real o caso concreto)*

```
S — "En [producto anterior], teníamos clientes que llevaban años 
     usando el canal presencial. Para ellos el ejecutivo era la garantía 
     de que el proceso funcionaría."

T — "Tenía que migrar ese segmento sin perder la confianza que habían 
     construido con el canal físico."

A — "Identifiqué dos causas distintas de resistencia y las traté diferente:

     Para la DESCONFIANZA:
     No intenté convencer — demostré. Arranqué con los clientes que ya 
     tenían la mejor relación con el banco, los usé como referentes, 
     y mostré los resultados en números: tiempo, costo, seguridad.
     Cuando un cliente satisfecho le dice a otro 'funcionó', pesa más 
     que cualquier campaña de marketing.

     Para la FRICCIÓN:
     Si alguien prefería ir a la sucursal porque el proceso digital era 
     complicado, el problema era mío, no del cliente. Cada abandono en 
     el flujo digital era una oportunidad de simplificar. 
     El digital tiene que ser más fácil, no solo más rápido."

R — "Resultado: [X% de los clientes piloto completaron al menos una 
     operación digital en los primeros 30 días / NPS del canal digital 
     superó al presencial en N puntos]."
```

---

## 3. PREGUNTAS QUE TÚ DEBES HACERLE AL HIRING

Estas preguntas demuestran que piensas como PM senior:

```
1. "¿Cuál es el mayor bloqueador hoy para que este producto esté en digital?
    ¿Es técnico, regulatorio, o de adopción del cliente?"

2. "¿Tienen data del funnel actual del canal presencial?
    ¿Saben en qué paso se cae la gente?"

3. "¿El squad de desarrollo ya existe o se forma para este producto?"

4. "¿Cuál es la métrica que el negocio usa hoy para medir el éxito del 
    producto de Factoring? ¿Volumen, margen, NPS?"

5. "¿Qué tan rígidos son los tiempos de compliance para aprobar nuevas 
    funcionalidades digitales? ¿Han hecho esto antes con otros productos?"

6. "¿Cuál sería el primer hito que me diría que estoy teniendo éxito 
    en los primeros 6 meses?"
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

### STAR (base de todas las respuestas)
```
S - Situation  → Contexto específico (empresa, momento)
T - Task       → Qué tenías/tendrías que lograr
A - Action     → Qué hiciste/harías tú específicamente (pasos concretos)
R - Result     → Resultado medible (número, tiempo, %)
```

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

### Tu framework propio de canales (verbalizar así)
```
"Mi punto de partida siempre es la data del canal: volumen, tiempos 
por paso, tasa de éxito. Con eso en la mano, hago 8-10 entrevistas 
para construir el journey completo. De ahí saco el As-Is con fricciones 
cuantificadas — y recién diseño el To-Be. No antes."

Paso 1: Baseline Analysis     → data del canal actual
Paso 2: Discovery cualitativo → 8-10 entrevistas usuarios + ejecutivos
Paso 3: As-Is mapeado         → journey con tiempos y fricciones
Paso 4: Pain point mapping    → fricciones priorizadas por impacto
Paso 5: To-Be digital         → blueprint del canal objetivo
```

---

## 6. CHECKLIST PRE-ENTREVISTA

```
□ Practica Q1-Q12 en voz alta usando estructura STAR
□ Prepara 3 historias STAR con números reales de tu experiencia
□ Investiga la empresa: ¿tienen app? ¿cómo está su Factoring hoy?
□ Lee sobre factura electrónica SUNAT (sistema OSE/PSE)
□ Estudia el journey de un competitor (BCP, BBVA, Interbank)
□ Prepara tus 6 preguntas para el hiring manager
□ Ten tu NSM preparado: "el éxito de este producto se mide con X porque..."
□ Practica "fricciones" en voz alta — no "flexiones"
□ Ensaya el cierre de Q1: termina con valor para la empresa, no para ti
```
