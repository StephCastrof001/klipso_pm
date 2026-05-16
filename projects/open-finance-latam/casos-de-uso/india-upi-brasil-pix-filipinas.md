# Case Study: Infraestructura de Pagos e Inclusion Financiera
## India (UPI) · Brasil (PIX) · Filipinas (GCash/InstaPay)

---

## Resumen ejecutivo

Tres casos donde infraestructura publica de pagos + regulacion mandatoria
eliminaron barreras de bancarizacion. Patron comun: rails publicos, innovacion privada encima.

---

## INDIA — UPI (2016)

### Antes
- 35% adultos bancarizados (2011)
- 318M cuentas Jan Dhan abiertas pero DORMIDAS — sin capa digital
- Pagos fragmentados, sin interoperabilidad

### Arquitectura (India Stack)
```
DigiLocker (documentos)
Aadhaar eKYC (identidad biometrica)
UPI (pagos real-time, interoperables)
Account Aggregator - AA (datos con consentimiento)
OCEN (protocolo credito embebido)
ONDC (comercio digital descentralizado)
```

### APIs UPI
| API | Funcion |
|---|---|
| Payment initiation | Push/pull P2P y P2M |
| UPI AutoPay | Pagos recurrentes |
| UPI 123PAY | Sin internet, telefono basico |
| UPI Lite | Offline, bajo valor |
| Credit on UPI | Tarjeta credito linkeada |

### Productos construidos
PhonePe (47% share), Google Pay (36%), BharatPe (12M merchants), KreditBee via OCEN

### Resultados
- 20.47B transacciones/mes (Nov 2025)
- 35% → 80%+ bancarizado
- 81% de pagos digitales retail en India

---

## BRASIL — PIX (Nov 2020)

### Antes
- TED/DOC: solo horario bancario, R$10-30/transferencia
- 77% pagos en efectivo (2019)
- 34M sin cuenta bancaria

### Arquitectura
```
SPI - Sistema de Pagamentos Instantâneos (BCB)
Chave PIX (CPF/celular/email — sin numero de cuenta)
PIX Garantido (BNPL, 2023)
PIX Automatico (suscripciones, 2024)
Open Finance (60M consents, 100B API calls/mes)
PIX Internacional (cross-border, 2025)
```

### Decisiones clave de diseno
- Gratuito para personas (BCB mandato precio cero)
- Participacion OBLIGATORIA bancos +500K clientes
- 24/7/365, liquida en <10 segundos

### Catalizador COVID
Auxilio Brasil entregado via PIX -> onboarding masivo poblacion de bajos ingresos

### Resultados
- 100M usuarios en 9 meses (mas rapido que WhatsApp en Brasil)
- 170M usuarios — 91% de adultos brasilenhos
- Cash: 77% → 22% de pagos (2024)
- 40M antes no bancarizados usaron PIX como primer producto financiero

---

## FILIPINAS — GCash / InstaPay (2018-2020)

### Antes
- 71% adultos sin cuenta bancaria (2019) — caso mas extremo
- Remesas OFW con 5-8% comision
- Sin rails de pago interoperables

### Arquitectura
```
BSP regulador
PESONet (batch) + InstaPay (tiempo real 24/7)
QR Ph (QR estandar unico)
GCash: wallet + GCredit + GInvest + GInsure + GSave
Maya Bank (banco digital full, 2022)
```

### Catalizador COVID
Gobierno entrego pagos sociales (Ayuda) EXCLUSIVAMENTE via GCash
-> onboarding masivo forzado poblacion rural

### Resultados
- GCash: 20M → 94M usuarios en 3 anos
- No bancarizados: 71% → 44% en 5 anos
- Pagos digitales superaron 52% del total (2024)

---

## Tabla comparativa

| Dimension | India UPI | Brasil PIX | Filipinas GCash |
|---|---|---|---|
| Builder rails | NPCI semi-publico | BCB banco central | BSP regulador |
| Unbanked antes | 65% | 16% | 71% |
| Unbanked despues | ~20% | ~9% | ~44% |
| Velocidad 100M | 3.5 anos | 9 meses | 3 anos |
| API mas poderosa | OCEN credito | Open Finance 100B calls | QR Ph + Open Finance |
| Palanca onboarding | Jan Dhan gratuito | Obligatorio + gratis | Pagos COVID |

---

## 5 patrones que se repiten

1. **Rails publicos, innovacion privada** — BCB/NPCI/BSP ponen la autopista, fintechs ponen los autos
2. **Obligatorio > voluntario** — Mexico CoDi voluntario fracaso, Brasil PIX obligatorio = 91% adultos
3. **Gratis para usuario** — cada fee genera dropout en segmentos bajos ingresos
4. **Alias > numero de cuenta** — CPF/celular/email reduce abandono en onboarding
5. **Credito es el producto final** — pagos son commodity, el valor = historial de tx -> acceso a credito

---

## Relevancia para LATAM

Peru (Yape), Colombia (Nequi/Daviplata), Mexico (DiMo) estan replicando estos patrones
en distintas etapas. La ventana de oportunidad de producto esta en la capa de credito
y educacion financiera encima de estos rails.

