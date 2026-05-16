# Open Finance LATAM — API Dashboard

> Mapa comparativo de APIs de Open Finance en America Latina:
> que datos exponen, quien las regula, y que productos se pueden buildear encima.

Autor: proyecto de aprendizaje PM — iniciado 2026-03-30
Fuente de investigacion: reguladores oficiales + agregadores privados

---

## Por que existe este repo

No hay un lugar unico donde un PM, developer o founder pueda ver:
- Que APIs de open finance existen en cada pais de LATAM
- En que estado regulatorio estan
- Que datos exponen
- Que productos ya se construyeron encima
- Que gaps quedan por resolver

Este repo es ese lugar.

---

## Estado por pais

| Pais | Regulacion | Datos transaccionales | Iniciacion de pagos | Estado |
|---|---|---|---|---|
| Brasil | Open Finance Brasil (BCB) | LIVE desde ago 2021 | LIVE via PIX | LIVE / REGULADO |
| Mexico | Ley Fintech Art. 76 (CNBV) | NO implementado (+2170 dias de retraso) | No regulado | PARALIZADO |
| Colombia | Sistema Finanzas Abiertas (URF+SFC) | Decreto mandatorio en proceso | No definido | EN PROGRESO |
| Peru | Sin regulacion publicada (SBS evaluando) | Sin borrador | Sin borrador | PLANIFICADO |
| Argentina | Sin framework formal | Bilateral privado | Bilateral | SIN MARCO |

---

## Agregadores regionales

| Agregador | Paises | Modelo | Funding |
|---|---|---|---|
| Belvo | MX, BR, CO, AR, CL, PE, UY | TPP regulado (BR) + bilateral | $70M+ (Kaszek, Visa, Citi) |
| Prometeo | 11 paises + US | Credential-based + bilateral | - |
| Syncfy | MX, CO + LATAM | B2B banking + fiscal data | - |
| Finerio Connect | MX | White-label PFM B2B | $6.5M (Third Prime) |

---

## Contenido del repo

```
open-finance-latam/
├── README.md                    <- este archivo
├── apis/
│   ├── brasil.md                <- Open Finance Brasil completo
│   ├── mexico.md                <- Ley Fintech + estado actual
│   ├── peru.md                  <- SBS + ecosistema Yape
│   └── colombia.md              <- Decreto mandatorio 2025
├── comparativa/
│   └── tabla_comparativa.md     <- la pieza mas compartible
└── casos-de-uso/
    ├── india-upi-brasil-pix-filipinas.md   <- benchmarks globales
    ├── peru-yape-covid-oportunidad.md      <- analisis Peru
    └── productos_posibles.md               <- que se puede buildear
```

---

## Referencias

- BCB Open Finance Brasil: https://www.bcb.gov.br/en/financialstability/open_finance
- Belvo docs: https://belvo.com
- Prometeo API: https://prometeoapi.com
- Colombia decreto URF Nov 2025: Syncfy analysis
- Fiskil Open Finance Tracker LATAM: https://www.fiskil.com
