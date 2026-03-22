# PATCH --- SOI-QUANT v1.2

## Layer Ascorbico di Tracciabilità e Compensazione

**Versione:** v1.1\
**Stato:** Patch sperimentale subordinata\
**Data:** Marzo 2026

**Prerequisiti:**

-   SOI-KERNEL (immutabile)\
-   SOI-STS (Valuation Engine)\
-   SOI-PM (Pressure Map)\
-   SOI-COMPASS (Regime Context)\
-   SOI-SW (Stability Window)\
-   SOI-IL (Incoherence Log)\
-   SOI-RL (Research Log)

------------------------------------------------------------------------

# 1. Scopo

Il presente **PATCH Ascorbico** introduce un layer matematico di
**tracciabilità delle tensioni** all'interno del SOI.

Le formule servono a rendere più leggibili:

-   divergenze di valore\
-   intensità delle pressioni\
-   fragilità della finestra di stabilità\
-   range di sostenibilità della size\
-   capacità di assorbimento dell'incoerenza

Il PATCH **non produce decisioni operative**.

Le formule hanno funzione esclusivamente:

-   descrittiva\
-   compensativa\
-   auditabile\
-   reversibile\
-   non prescrittiva

------------------------------------------------------------------------

# 2. Principio di subordinazione

Il **Layer Ascorbico** è subordinato al **SOI-KERNEL**.

Il Kernel resta l'unico luogo in cui può emergere una decisione.

Gli output del PATCH devono essere interpretati come:

-   tracce di tensione\
-   tracce di fragilità\
-   tracce di sostenibilità\
-   tracce di assorbimento

e mai come:

-   segnali buy/sell\
-   regole operative\
-   soglie decisionali\
-   logiche binarie\
-   sistemi di ottimizzazione

------------------------------------------------------------------------

# 3. Compliance con i vincoli del SOI

Il PATCH rispetta i principi non negoziabili del sistema:

-   nessuna logica **if/then**
-   nessuna soglia operativa
-   decisione emergente solo dal Kernel
-   **IC-1 sempre attiva**
-   centralità della **size come range**
-   mantenimento dell'incoerenza strutturale
-   nessuna eliminazione delle divergenze
-   compatibilità con AMC

------------------------------------------------------------------------

# 4. Collocazione architetturale

Il PATCH non è un modulo indipendente.

È uno **strato trasversale di lettura** che si appoggia ai moduli del
sistema.

STS / PM / Compass / SW / Risk / IL\
↓\
PATCH ASCORBICO (tracce matematiche)\
↓\
SOI-KERNEL\
↓\
Allocation Move emergente

Il PATCH **non interagisce direttamente con il portafoglio**.

------------------------------------------------------------------------

# 5. Famiglie di output del PATCH

## Tracce di divergenza

-   Valuation Range\
-   MOS variabile\
-   Tension Incoherence Trace (TI)

## Tracce di pressione

-   Pressure Trace\
-   Pressure Load Trace

## Tracce di fragilità

-   Fragility Trace\
-   Correlation Drift Trace\
-   Drawdown Absorption Range

## Tracce di sostenibilità

-   Sustainable Weight Interval\
-   Risk Budget Sustain Range

------------------------------------------------------------------------

# 6. Integrazione in SOI-STS --- Valuation Engine

### Formula DCF

V = Σ FCFF_t / (1 + WACC)\^t + TV / (1 + WACC)\^n

### Output

Valuation Range:

V_range = \[V_bear , V_bull\]

MOS variabile:

MOS_var = (V_mid - Price) / V_mid

V_mid = (V_bear + V_bull) / 2

MOS è una **traccia di compressione prezzo-valore**, non un segnale di
acquisto.

------------------------------------------------------------------------

# 7. Pressure Map

Pressure Trace:

PT = (E × S) / (1 + U)

dove:

-   E = peso evidenza\
-   S = sensibilità\
-   U = incertezza

Interpretazione relativa rispetto alle altre pressioni attive.

------------------------------------------------------------------------

# 8. Fragility Trace

FT = ( Σ D_s − Σ T_i ) / (K + 1)

dove:

-   D_s = driver stabilità\
-   T_i = trigger instabilità\
-   K = kill switch

Serve solo a descrivere la forma della **Stability Window**.

------------------------------------------------------------------------

# 9. Sustainable Weight Interval

SWI = \[w_min , w_max\]

SWI = w_attuale × ( 1 ± (MOS_var × (1 − FT)) / (1 + PLT_bloccanti) )

SWI rappresenta il **perimetro di sostenibilità**, non il peso target.

------------------------------------------------------------------------

# 10. Risk Budget Sustain Range

RB_sustain = RB_base × Multiplier_range × (1 / Attrito_Compass)

Descrive come il regime comprime o espande il rischio sostenibile.

------------------------------------------------------------------------

# 11. Correlation Drift

CDT = \|ρ_norm − ρ_stress\| × C_f

Serve a evidenziare **falsa diversificazione**.

------------------------------------------------------------------------

# 12. Drawdown Absorption

DD_abs = DD_storico × R_f × (1 − F_sistemica)

Descrive la tolleranza al drawdown.

------------------------------------------------------------------------

# 13. Incoherence Log --- Tension Index (v1.2)

Il sistema utilizza il **Tension Index vettoriale v1.2** (norma euclidea per maggiore robustezza multidimensionale):

\[
TI_{tot}^{v1.2} = \sqrt{TI_{val}^2 + TI_{narr}^2 + TI_{ciclo}^2 + TI_{tec}^2}
\]

dove:

- \( TI_{val} = \frac{|V_{prudente} - V_{narrativo}|}{V_{mid}} \times (1 - MOS) \)  
  (tensione valore canonica IC-1)

- \( TI_{narr} = \frac{|N_{mercato} - N_{propria}|}{N_{media}} \)  
  (tensione narrativa – Reverse DCF vs narrativa propria)

- \( TI_{ciclo} = \frac{|Sens_{ciclo} \times DD_{toll}|}{Time-to-Error_{agg}} \)  
  (tensione ciclica – Marks)

- **Nuova componente**  
  \( TI_{tec} = \frac{VC \times Attrito_{Compass}}{Reversibilità_{tecnica}} \)  
  (tensione tecnica – Valuation Compression × attrito dal SOI-COMPASS §4)

Il sistema resta valido solo se \( TI_{tot}^{v1.2} > 0.15 \) (almeno una incoerenza visibile).

**Output obbligatorio in IL:**
- TI_val = X.XX
- TI_narr = X.XX
- TI_ciclo = X.XX
- TI_tec = X.XX
- TI_tot v1.2 = X.XX
- Modalità di assorbimento adottata: “size adattiva × MOS variabile × compensazione cross-pressure”

**Nota di versioning:**  
Il passaggio da v1.1 (moltiplicativo) a v1.2 (euclidea) aumenta la capacità di assorbimento senza introdurre nessuna soglia decisionale.

------------------------------------------------------------------------

# 14. Output verso il Kernel

Il PATCH invia al Kernel solo:

-   Valuation Range
-   MOS_var
-   Pressure Trace
-   Pressure Load Trace
-   Fragility Trace
-   Sustainable Weight Interval
-   Risk Budget Sustain Range
-   Correlation Drift Trace
-   Drawdown Absorption Range
-   TI vector

Il Kernel stabilizza queste tensioni.

------------------------------------------------------------------------

# 15. Identità del Layer Ascorbico

> Il Layer Ascorbico non riduce l'incertezza in decisione.\
> Rende misurabile quanta incertezza il sistema sta assorbendo.
