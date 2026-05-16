# Tabla Comparativa — Open Finance LATAM
> La pieza mas compartible del repo. Actualizar cuando cambien los estados regulatorios.

---

## Estado regulatorio por pais

| Pais | Regulacion | Regulador | Datos transaccionales | Iniciacion pagos | Estado |
|---|---|---|---|---|---|
| Brasil | Open Finance Brasil (BCB Res. 400) | BCB + CMN + AOF | LIVE ago 2021 | LIVE via PIX oct 2021 | LIVE / REGULADO |
| Mexico | Ley Fintech Art. 76 (LRITF 2018) | CNBV + Banxico | NO (+2,170 dias retraso) | No regulado | PARALIZADO |
| Colombia | Sistema Finanzas Abiertas (URF) | URF + SFC | Decreto en proceso (nov 2025) | No definido | EN PROGRESO |
| Peru | Sin regulacion publicada | SBS evaluando | Sin borrador | Sin borrador | PLANIFICADO |
| Argentina | Sin framework formal | BCRA | Bilateral privado | Bilateral | SIN MARCO |

---

## Agregadores regionales

| Empresa | Paises | Modelo | Funding | Escala |
|---|---|---|---|---|
| Belvo | MX BR CO AR CL PE UY | TPP regulado (BR) + bilateral | $70M+ (Kaszek, Visa, Citi) | 15M consents BR, 80M emp checks MX |
| Prometeo | 11 paises + US | Credential-based + bilateral | - | 7,500+ conexiones bancarias |
| Syncfy | MX CO + LATAM | B2B banking + fiscal | - | - |
| Finerio Connect | MX | White-label PFM B2B | $6.5M (Third Prime) | - |

---

## Que datos expone cada pais HOY

| Tipo de dato | Brasil | Mexico | Colombia | Peru |
|---|---|---|---|---|
| Productos/tasas publicas | SI | SI | SI | No estandar |
| Balances de cuenta | SI | NO | NO aun | NO |
| Historial transacciones (24m) | SI | NO | NO aun | NO |
| Historial crediticio | SI | Parcial via buro | NO aun | NO |
| Inversiones/seguros/pension | SI | NO | NO aun | NO |
| Iniciacion de pago (PIX/similar) | SI | NO | NO aun | NO |

---

## Benchmarks globales de referencia

| Pais | Sistema | Unbanked antes | Unbanked despues | Transacciones/mes | Velocidad adopcion |
|---|---|---|---|---|---|
| India | UPI (2016) | 65% | ~20% | 20.47B | 100M usuarios en 3.5 anos |
| Brasil | PIX (2020) | 16% | ~9% | ~8B | 100M usuarios en 9 meses |
| Filipinas | GCash/InstaPay (2018) | 71% | ~44% | PHP 2.6T valor | 94M usuarios en 3 anos |

---

## Patron de exito — los 5 factores comunes

| Factor | India | Brasil | Filipinas | LATAM status |
|---|---|---|---|---|
| Rails publicos, innovacion privada | SI (NPCI) | SI (BCB) | SI (BSP) | Solo Brasil |
| Participacion obligatoria | SI | SI | SI | Solo Brasil |
| Gratuito para usuario | SI | SI | SI | Parcial (Yape gratis) |
| Alias > numero de cuenta | SI (VPA) | SI (Chave PIX) | SI (QR Ph) | Parcial (Yape = celular) |
| Credito como producto final | SI (OCEN) | SI (Open Finance) | SI (GCredit) | Pendiente |

---

## Oportunidades de producto por pais

### Brasil (Capa 3-4 activa)
- Underwriting automatico con 24 meses historial transacciones
- PIX Garantido (BNPL) embebido en apps no financieras
- Consolidacion de portafolio de inversiones multi-broker

### Mexico (workarounds mientras espera regulacion)
- Underwriting con datos SAT/CFDI para empresas que facturan
- Verificacion de ingresos para empleados formales (IMSS)
- Educacion financiera para segmentos excluidos por falta de RFC/RUC

### Colombia (prepararse para post-decreto)
- Agregador de cuentas multi-banco
- Comparador de seguros con datos reales
- Credito para economia informal (~50% fuerza laboral)

### Peru (capa de pagos + educacion)
- Microcredito para bodegueros con historial Yape
- Educacion financiera contextual para usuarios informales
- Comparador de productos financieros por perfil de usuario
