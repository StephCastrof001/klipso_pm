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

*(Comportamental — historia real de Ágora, dos versiones según contexto)*

---
**VERSIÓN A — Si el rol es 0-to-1 (construir desde cero):**
```
S — "Soy PM con 10 años de experiencia en productos digitales.
     En Ágora fui parte del equipo fundador: construimos el canal 
     digital desde cero, sin canal tradicional previo, sin data 
     histórica, sin flujos que adaptar. Nadie en la empresa había 
     hecho esto antes."

T — "Mi tarea era diseñar el canal completo — entender al usuario 
     sin ningún baseline y validar los flujos antes de construir."

A — "Sin data histórica, mi primer instrumento fue el discovery 
     cualitativo: entrevistas a usuarios para entender sus retos reales.
     Con eso construí el As-Is y el To-Be desde cero, sin asumir nada.
     Luego conduje mesas de validación con el equipo para asegurar 
     que lo que íbamos a construir resolvía el problema correcto 
     antes del primer sprint."

R — "El canal se lanzó en 3 meses. Arrancamos en Trujillo, 
     luego Lima, luego Piura. En los primeros 6 meses generamos 
     más de S/3 millones en ventas."
```
**Cierre:**
> *"Me interesa este rol porque es exactamente ese tipo de reto: construir desde cero, sin canal tradicional que sirva de guía. Las facturas SUNAT ya están digitalizadas — la infraestructura existe. Lo que falta es el canal y el PM que lo construya. Es el escenario donde he demostrado resultados."*

---
**VERSIÓN B — Si el rol es migración de canal tradicional a digital:**
```
S — "Soy PM con 10 años de experiencia. En Ágora lideré el pivote 
     de un producto retail a un producto financiero dentro del 
     ecosistema de Intercortel. Ya teníamos procesos digitales 
     armados — customer journeys, estrategia por segmentos — 
     pero todo debía rehacerse para el nuevo dominio financiero."

T — "Mi tarea fue liderar el rediseño completo del canal: 
     entender el ecosistema financiero nuevo y construir los 
     flujos que lo soportaran desde la data hasta el piloto."

A — "Lo estructuré en cuatro pasos:
     Primero, analicé la data del canal actual para establecer el baseline.
     Segundo, hice entrevistas a usuarios y stakeholders para mapear 
     el journey con fricciones cuantificadas.
     Tercero, construí el As-Is y el To-Be.
     Cuarto, conduje mesas ágiles para validar con stakeholders 
     y empujar los pilotos."

R — "Creamos más de 10 productos financieros nuevos.
     Ágora se posicionó como player relevante en Intercortel.
     Superamos el objetivo de canal: más de S/60 millones en 
     ingresos con gastos acotados."
```
**Cierre:**
> *"Me interesa este rol porque el Descuento Electrónico en Perú está en el mismo punto de inflexión que Ágora cuando entré: la infraestructura técnica ya existe — SUNAT ya digitaliza las facturas — pero la experiencia del cliente sigue siendo presencial. Quiero aportar en este momento específico porque es exactamente el tipo de transición en la que he demostrado resultados."*

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
     La infraestructura ya existe. Falta el canal.
     Y lo confirma mi experiencia en Ágora: cuando construimos el canal 
     financiero dentro del ecosistema de Intercortel, el mayor reto no fue 
     la integración técnica — fue diseñar la experiencia para que los clientes 
     confiaran en el canal sin el ejecutivo presencial de por medio. 
     Cuando resolvimos eso, llegamos a S/60 millones en ingresos."
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

R — "En Ágora, este proceso — baseline + 8 entrevistas + As-Is con fricciones 
     cuantificadas — nos tomó 3 semanas y nos ahorró 2 sprints de desarrollo 
     al evitar construir features que los clientes no iban a usar.
     Para el canal de Factoring: antes del primer sprint, 3 fricciones 
     priorizadas por impacto cuantificado y validadas con 5 clientes."
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

R — "Reducción de 3-5 días a menos de 4 horas.
     Fricciones eliminadas: desplazamiento x2, caja negra, proceso manual, 
     incertidumbre de desembolso.
     El argumento que convence a los stakeholders no es el diseño — 
     es el cálculo: una PyME que descuenta 10 facturas al mes pierde 
     30-50 días productivos solo en idas a sucursal. Eso es capital de trabajo.
     En Ágora, este análisis fue lo que movió al negocio a invertir 
     en el canal digital — y ese canal llegó a S/60 millones en ingresos."
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

R — "En Ágora hicimos exactamente esto en el lanzamiento del canal 
     en Trujillo — primer piloto del canal digital.
     Lanzamos con funciones mínimas: subir factura + ver estado de solicitud.
     Sin firma digital avanzada, sin operaciones múltiples, sin historial.
     3 meses para lanzar. S/3 millones en ventas en 6 meses.
     Lo que dejamos para V2 nunca fue bloqueante para los primeros clientes.
     La automatización llegó en el ciclo siguiente, cuando el piloto la justificó."
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

R — "En Ágora, esta metodología nos permitió lanzar más de 10 productos 
     financieros nuevos dentro del ecosistema de Intercortel sin que 
     un bloqueador de compliance detuviera ningún sprint.
     El roadmap era legible para negocio, anticipable para legal, 
     y ejecutable para tecnología — los tres a la vez."
```

---

**Q9: Traduce este requerimiento a historias de usuario:**
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

R — "En Ágora, este proceso nos evitó el re-trabajo más costoso: 
     construir algo que el equipo técnico entendía diferente al negocio.
     Con criterios de aceptación explícitos desde el refinamiento, 
     los sprints no se usaban para clarificar — se usaban para entregar.
     El equipo puede estimar, implementar y verificar.
     El negocio sabe exactamente qué se construye y cuándo.
     Y si la data no justifica la V2 automática, la historia no entra al backlog."
```

---

**Q10: ¿Cómo manejas conflictos entre tecnología y negocio?**

*(Comportamental — usa STAR con ejemplo concreto)*

```
S — "En el lanzamiento del canal digital de Ágora, compliance exigía 
     que todos los contratos llevaran firma manuscrita escaneada.
     Tecnología había diseñado el flujo completo con firma digital OTP.
     Ambos tenían razón dentro de su dominio — compliance por el riesgo 
     regulatorio, tecnología por la experiencia del usuario."

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

R — "Lanzamos en fecha con firma OTP en Trujillo.
     Los 10 clientes piloto completaron contratos sin ningún bloqueador 
     regulatorio — OTP cumplía el estándar de trazabilidad para el 
     rango de montos del piloto.
     V2 con firma avanzada certificada entró en el trimestre siguiente, 
     cuando el volumen del canal lo justificó."
```

---

### BLOQUE D: Ceremonias Ágiles

---

**Q9: ¿Cómo describes tu rol en cada ceremonia del squad?**

*(Comportamental — historia real de Ágora con squad ágil)*

```
S — "En Ágora trabajé con un squad ágil donde la PM era el único 
     punto de contacto entre tecnología, negocio y el cliente.
     Si yo no estaba disponible en el momento correcto, 
     el equipo se bloqueaba."

T — "Definí un rol específico para cada ceremonia para que el equipo 
     pudiera avanzar sin esperar decisiones de último minuto."

A — "Así lo ejecuté en Ágora:

     REFINAMIENTO (la más importante — 1-2h por semana):
     Traducía las hipótesis de negocio en historias de usuario 
     con criterios de aceptación verificables.
     El equipo que entiende el PORQUÉ de una feature toma mejores 
     micro-decisiones durante el desarrollo — sin consultarme cada hora.
     Si una historia llegaba sin AC claro → la devolvía, no la refinaba.

     SPRINT PLANNING (2-4h):
     Mi regla: ninguna historia entra al sprint sin criterios de 
     aceptación claros. Si algo llega sin ellos → sale del sprint.
     Mejor dejar la historia para el siguiente ciclo que construir 
     algo que nadie sabe cómo verificar.

     DAILY (15 min):
     Mi rol es escuchar blockers — no reportar status.
     Si un developer está bloqueado por una definición de negocio 
     → la resuelvo ese día, no mañana.
     Cada día que un blocker queda abierto es un día de sprint perdido.

     REVIEW (1h):
     Represento la voz del cliente.
     Pregunta que siempre hago: '¿el cliente entendería este flujo 
     sin que nadie se lo explique?'

     RETROSPECTIVA:
     Participo como miembro del equipo, no como jefe.
     Hablo de proceso, no de personas ni de resultados de negocio."

R — "El resultado en Ágora: el squad entregó todas las releases 
     planificadas y superamos los objetivos en un 20%.
     El equipo no me esperaba para avanzar porque las preguntas 
     se resolvían en refinamiento, no en medio del sprint."
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
     Los 10 clientes piloto completaron sus operaciones sin fricciones 
     — no notaron que la validación SUNAT era manual en el backend.
     La integración automática entró en el siguiente sprint, 
     cuando el equipo ya tenía la documentación de la API completa.
     Lección de Ágora: si el workaround no tiene un criterio explícito 
     de cuándo automatizarlo, se vuelve permanente.
     Criterio documentado: cuando el 50% de las operaciones piloto 
     sean autoservicio completo, la automatización SUNAT pasa a Tier 1."
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

R — "El riesgo de adopción se mitiga antes del lanzamiento, no después.
     En Ágora usamos exactamente esta lógica: arrancamos en Trujillo 
     — la ciudad más conservadora del grupo piloto — para probar el 
     caso más difícil primero. El canal pasó el threshold de adopción.
     Escalamos a Lima y Piura con evidencia, no con esperanza.
     El resultado: S/3 millones en ventas en 6 meses.
     Criterio de go/no-go para Factoring: si el 40% de los clientes 
     piloto completa la primera operación sin ayuda humana, 
     el canal es viable para escalar."
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
     Eso indica que estamos captando un segmento nuevo, no canibalizando 
     el canal existente.
     En Ágora el pivote financiero siguió este patrón: el canal digital 
     no compitió frontalmente con el presencial al inicio — captó las 
     operaciones de menor complejidad y fue ganando terreno con la frecuencia.
     S/60 millones en ingresos con gastos acotados fue el resultado 
     de esa estrategia de canal diferenciado."
```

---

**Q16: ¿Qué harías en los primeros 30-60-90 días?**

*(Comportamental — historia real de Ágora aplicada al contexto Factoring)*

```
S — "Llego a un producto financiero que opera 100% en canal presencial.
     Hay una organización con equipos formados — tecnología, crédito, 
     comercial, compliance — compromisos ya tomados, y un cliente 
     PyME que confía en el ejecutivo humano más que en cualquier app."

T — "En 90 días necesito entender el problema real sin asumir nada, 
     alinear a los stakeholders, y tener un piloto en manos de 
     clientes reales."

A — "Estructuro en tres fases — exactamente como lo hice en Ágora:

     DÍA 1-30: DATA Y CAMPO (no construir nada todavía)
     — Analizo la data del canal actual: volumen mensual de operaciones,
       tiempo por paso, tasa de aprobación, monto promedio, drop-off.
       Esto me da el baseline antes de hablar con nadie.
     — 10 entrevistas: 4 clientes actuales del canal presencial,
       3 ejecutivos de sucursal, 2 del área de crédito, 1 de compliance.
       Pregunta clave: '¿cuándo necesitaste liquidez urgente y qué fue 
       lo más frustrante del proceso?'
     — Shadow en sucursal: ver el proceso en vivo, no leer sobre él.
     — 1:1 con cada área para entender compromisos ya tomados 
       y el roadmap existente.

     DÍA 31-60: DIAGNÓSTICO Y MVP
     — Mapeo el journey completo con tiempos y fricciones cuantificadas.
     — Aplico Pareto: el 20% de fricciones que explica el 80% del 
       tiempo perdido — esas son las primeras en el backlog.
     — Sizing: cuánto volumen tiene el canal presencial hoy, 
       cuánto cuesta por operación, cuánto puede mejorar el digital.
     — Propongo el MVP y lo valido con 5 clientes antes de escribir 
       una sola historia de usuario.
       En Ágora esta validación nos ahorró 2 sprints de desarrollo.

     DÍA 61-90: PILOTO Y PRIMERA SEÑAL
     — Primer sprint con el equipo.
     — Establezco la línea de base de los KPIs: tasa de adopción 
       digital, FCR, SLA, activation rate.
     — Lanzo piloto con 10-20 clientes seleccionados — los de mayor 
       NPS con el canal presencial, no los escépticos.
     — Primera review con stakeholders: datos, no promesas."

R — "Al día 90: canal digital en manos de clientes reales,
     métricas base establecidas, y la primera señal de si el 
     approach es correcto o necesita ajuste.
     En Ágora este ciclo nos llevó a S/3M en ventas en 6 meses."
```

---

**Q14: ¿Cómo manejas la resistencia de clientes a migrar al canal digital?**

*(Comportamental — historia real de Ágora, contexto financiero)*

```
S — "En Ágora cuando lanzamos el canal digital, los primeros clientes 
     llevaban meses operando con el ejecutivo presencial.
     Para ellos el ejecutivo no era un canal — era la garantía de 
     que su operación iba a salir bien.
     Pedirles que usaran una app era pedirles que confiaran en algo 
     que no podían ver ni tocar."

T — "Tenía que migrar ese segmento sin perder la confianza que 
     habían construido con el canal físico."

A — "Diagnostiqué dos causas distintas y las traté diferente:

     DESCONFIANZA (el cliente no cree que el digital funcione):
     No convencer — demostrar. Empecé con los clientes que ya 
     tenían el NPS más alto con el canal existente, no con los 
     escépticos. Los usé como pilotos y como referentes.
     Cuando un cliente dice a otro 'funcionó y me tomó 2 horas 
     en vez de 3 días' — eso vale más que cualquier campaña.

     FRICCIÓN (el cliente quiere usar el digital pero es difícil):
     Cada abandono en el flujo era mi responsabilidad, no del cliente.
     Si alguien prefería ir a la sucursal porque la app era 
     complicada, el problema era mío.
     Medía el drop-off por paso del funnel y atacaba el punto 
     de mayor abandono primero.
     Regla: si el usuario necesita leer instrucciones para completar 
     el flujo, el diseño falló."

R — "En Ágora arrancamos en Trujillo — la ciudad más conservadora 
     del grupo piloto — para probar el caso más difícil primero.
     El canal funcionó. Luego Lima, luego Piura.
     El canal se lanzó en 3 meses y en 6 meses generamos 
     S/3 millones en ventas."
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
