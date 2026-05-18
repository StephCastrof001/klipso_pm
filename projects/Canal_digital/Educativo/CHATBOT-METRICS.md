# Chatbot Metrics — PM Reference
> Métricas específicas para productos de IA conversacional.
> Complementa el pm-brain AARRR (que NO aplica directamente a chatbots).

---

## North Star por etapa del producto

| Etapa | North Star | Target mínimo | Señal de alarma |
|---|---|---|---|
| Piloto (días 1-30) | Containment rate | >50% | <40% → rediseñar antes de escalar |
| Estabilización (mes 2-3) | Resolution rate | >60% | <50% → revisar gaps en docs |
| Escala (mes 4+) | Cost per resolution | <$0.05 USD | >$0.15 → revisar modelo o rate limits |

---

## Las 6 métricas core

### 1. Containment Rate (North Star temprana)
**Qué es:** % de conversaciones resueltas sin escalar al humano.
**Fórmula:** `conversaciones_resueltas_bot / total_conversaciones × 100`
**Target:** >60% | Mínimo aceptable piloto: >50%
**Dónde medir:** langfuse traces + log de escalaciones
**Lo que revela:** si el bot tiene gaps de conocimiento o si los docs son incompletos.

### 2. Resolution Rate
**Qué es:** % de usuarios cuya necesidad quedó realmente resuelta.
**Diferencia con containment:** el bot puede contener (no escalar) pero el usuario se fue sin resolver.
**Fórmula:** `usuarios_satisfechos / total_conversaciones × 100`
**Target:** >55%
**Dónde medir:** CSAT post-conversación (👍/👎) + langfuse

### 3. Escalation Rate + punto de quiebre
**Qué es:** % de conversaciones que terminan en handoff al humano.
**Fórmula:** `escalaciones / total_conversaciones × 100`
**Target:** <20%
**Lo crítico:** no solo el %, sino **en qué paso del flujo** ocurre.
→ Si escalan en el paso 2 → el bot no entiende la intención inicial.
→ Si escalan en el paso 5 → llegan lejos pero el bot no puede cerrar.
**Dónde medir:** langfuse (tag de "escalation" en cada trace)

### 4. Hallucination Rate
**Qué es:** % de respuestas que contienen información incorrecta o inventada.
**Fórmula:** medición con ragas (faithfulness score < 0.7 = posible hallucination)
**Target:** <5% general | <1% en salud, finanzas, legal
**Dónde medir:** ragas pipeline + golden dataset manual
**Riesgo:** en dominios críticos, una hallucination puede tener consecuencias legales.

### 5. CSAT Post-Chat
**Qué es:** satisfacción del usuario al cerrar la sesión.
**Método:** botón 👍/👎 o escala 1-5 al final de la conversación.
**Target:** >75% positivo o >4.0/5
**Dónde medir:** anything-llm feedback widget / langfuse custom events

### 6. Cost per Resolution
**Qué es:** costo real de resolver una conversación (tokens + infra).
**Fórmula:** `(costo_tokens_conversación) / conversaciones_resueltas`
**Target:** <$0.05 USD con Gemini Flash | <$0.01 USD con Ollama local
**Dónde medir:** langfuse token tracking → calcula automáticamente

---

## Repos en esta carpeta relacionados

| Repo | Qué mide | Métricas cubiertas |
|---|---|---|
| `Call-Center-Analysis/` | KPIs de atención: CSAT, handle time, abandonment rate | 5, 3 |
| `Call-Centre-Calls-Prediction/` | Predicción de volumen de conversaciones | útil para capacity planning |
| `Customer-Support-Ticket-Analyzer/` | Routing accuracy, scoring por agente | 1, 2 |
| `edu_bot/evaluation/` | Evaluación de RAG: faithfulness, relevancy | 4 |

---

## Referencia cruzada
→ Framework completo: `klipso_pm/ai-product/AI-PRODUCT-FRAMEWORK.md`
→ Eval técnica: `klipso_pm/ai-product/ragas/`
→ Monitoring: `klipso_pm/ai-product/langfuse/`
