# Mexico — Ley Fintech / Open Finance

**Regulacion:** LRITF Art. 76 — promulgada 9 marzo 2018
**Regulador:** CNBV + Banxico + SHCP
**Estado:** PARALIZADO — Nivel 1 implementado, datos transaccionales con +2,170 dias de retraso

## Arquitectura de tres niveles

| Nivel | Nombre | Contenido | Estado |
|---|---|---|---|
| 1 | Datos Financieros Abiertos | Catalogos, tasas CAT/GAT, sucursales | IMPLEMENTADO jun 2021 |
| 2 | Datos Agregados | Estadisticos de portafolio, buros | PARCIAL |
| 3 | Datos Transaccionales | Balances, historial, ingresos con consentimiento | NO IMPLEMENTADO |

## Por que esta paralizado

- Fecha limite regulacion secundaria: marzo 2020
- Dias de retraso (feb 2026): +2,170 dias
- Enero 2026: amparo constitucional presentado contra CNBV/Banxico/SHCP
- CNBV con recortes presupuestarios + exodo de talento
- Sin entidad de implementacion (no hay equivalente al AOF de Brasil)
- Sin especificaciones tecnicas estandarizadas
- Sin ambiente de pruebas/certificacion

## Workarounds del mercado

| Workaround | Como funciona | Limitacion |
|---|---|---|
| Datos fiscales SAT (CFDI) | Belvo conecta SAT para obtener facturas como proxy de ingresos | Solo quienes facturan |
| Verificacion empleo IMSS | Registros empleo formal | Solo empleados formales |
| Integraciones bilaterales | Acuerdos banco-fintech directos | No escalable, cerrado |

## Agregadores activos

| Empresa | Escala | Modelo |
|---|---|---|
| Belvo | 80M+ verificaciones empleo, $1B TPV anualizado | Bilateral + SAT fiscal |
| Finerio Connect | B2B white-label PFM | Bilateral |
| Syncfy | Banking + fiscal data | Bilateral |
| Palenca | Verificacion gig workers | IMSS + plataformas gig |

## Productos posibles HOY

- Comparador de productos financieros (Datos Abiertos) — SI
- Underwriting con datos SAT — SI (parcial, solo quienes facturan)
- Verificacion de empleo/ingresos — SI (empleados formales)
- Agregacion de cuentas real — NO
- PFM multi-banco — NO
- Iniciacion de pagos estandar — NO

## Leccion para LATAM

Mexico muestra lo que pasa con regulacion voluntaria sin entidad de implementacion:
fragmentacion en silos privados, datos atrapados en bancos grandes, inclusion financiera estancada.
Contraste: Brasil obligatorio + AOF = 100B API calls/mes.
