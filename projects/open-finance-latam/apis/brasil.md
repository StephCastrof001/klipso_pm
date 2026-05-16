# Brasil — Open Finance Brasil

**Regulacion:** Joint Resolution CMN-BCB No. 1/2020 → BCB Resolution 400
**Regulador:** Banco Central do Brasil (BCB) + CMN
**Entidad de implementacion:** Associacao Open Finance Brasil (AOF)
**Estado:** LIVE / COMPLETAMENTE REGULADO — el ecosistema mas maduro de LATAM

---

## Fases de implementacion

| Fase | Datos | Lanzamiento |
|---|---|---|
| Fase 1 | Datos publicos: sucursales, ATMs, catalogos de productos, tasas | Feb 2021 |
| Fase 2 | Datos de cliente: cuentas, balances, historial de transacciones (24 meses), tarjetas | Ago 2021 |
| Fase 3 | Iniciacion de pagos: PIX, TED, DOC, boletos | Oct 2021 |
| Fase 4 | Finanzas extendidas: FX, inversiones, seguros, pension, nomina | Oct 2022–2023 |

---

## Datos expuestos (Fase 2 en adelante)

- Datos de registro del cliente
- Cuentas de deposito y saldo
- Operaciones de credito
- Historial de transacciones (24+ meses)
- Tarjetas de credito
- Inversiones (CDBs, depositos a plazo)
- Seguros y pension (previdencia)
- Cuentas de adquisicion/nomina

---

## Arquitectura tecnica

- Estandar de seguridad: FAPI (Financial-grade API) — perfil certificado BCB
- Consentimiento: gestionado por AOF, trazable
- Directorio de participantes: centralizado en AOF

---

## Metricas del ecosistema (2025)

| Metrica | Valor |
|---|---|
| Consentimientos activos | 61.9M (2024), 128M+ acumulados |
| Llamadas API mensuales | 100 billion/mes |
| Iniciacion de pagos 2024 | 159M llamadas (+194% YoY) |
| Crecimiento YoY consentimientos | +45% |

---

## PIX — la capa de pagos

| Elemento | Detalle |
|---|---|
| Lanzamiento | 16 noviembre 2020 |
| Liquidacion | <10 segundos, 24/7/365 |
| Costo usuario | GRATIS (BCB mandato) |
| Participacion | Obligatoria para bancos +500K clientes |
| Usuarios | 170M (~91% adultos brasilenhos) |
| Volumen mensual | ~8B transacciones/mes |
| Cash share | Bajo de 77% (2019) a 22% (2024) |

### APIs de PIX disponibles
- Initiacion de pago (push/pull)
- Chave PIX (alias: CPF, CNPJ, celular, email, clave aleatoria)
- PIX Garantido (BNPL, 2023)
- PIX Automatico (suscripciones, 2024)
- PIX Internacional (cross-border, 2025)

---

## Agregadores principales

| Empresa | Escala | Clientes |
|---|---|---|
| Belvo | 15M consentimientos activos (16% del total), 375% crecimiento 2025 | Inter, Alipay, Indrive |
| Sensedia | Gestion de APIs para grandes bancos | Bancos incumbentes |
| Quanto | Adquirido por XP Inc. | - |

---

## Productos que se pueden buildear encima

| Categoria | Producto | Capa requerida |
|---|---|---|
| Credito | Underwriting automatico con 24 meses de historial | Fase 2 |
| PFM | Agregacion de cuentas multi-banco | Fase 2 |
| Pagos | Iniciacion PIX embebida en apps no financieras | Fase 3 |
| Seguros | Comparacion y switch de seguros | Fase 4 |
| Inversiones | Consolidacion de portafolio multi-broker | Fase 4 |
| Finanzas embebidas | PIX + datos en apps de gig economy | Fase 2+3 |
| Credito consignado | Verificacion de ingresos real via nomina | Fase 4 |

---

## Que aprende LATAM de Brasil

1. Participacion OBLIGATORIA = red de efecto instantaneo
2. Gratis para usuarios = inclusion de segmentos bajos ingresos
3. Open Finance encima de PIX = el credito es el producto de valor real
4. BCB como dueno de la infraestructura = no oligopolio privado
