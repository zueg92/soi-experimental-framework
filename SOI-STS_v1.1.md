# SOI-STS — Single Title Subsystem
**Versione:** v1.1  
**Titolo:** [TICKER / NOME]  
**Data:**  
**Scopo:** Analizzatore fondamentale + tecnico con architettura tensionale di valutazione  
**Fonti teoriche:** Graham, Damodaran, Greenwald, Marks, Palat, Taylor  

---

## 0. Vincoli (Kernel compliance)

- Nessuna decisione BUY/SELL
- Nessuna soglia che “decide”
- Output = Pressioni + Stabilità + Allocazione candidata
- Valore intrinseco espresso come **RANGE**
- Incoerenza **IC-1** sempre attiva
- I modelli di valutazione generano **tensione**, non verità finale

---

## 1. Business & Industry Analysis (Palat)

### 1.1 Business model
- Come l’azienda guadagna (meccanismo chiave):
- Pricing power: nullo / debole / medio / forte
- Cost structure: fissa / variabile / mista

### 1.2 Industria & competitività
- Struttura settore:
- Barriere all’ingresso:
- Posizionamento competitivo:

**Output:** `Business Quality Pressure`

---

## 2. Accounting & Financial Reality (Graham)

### 2.1 Qualità utili
- Utile ↔ Cash Flow: coerente / divergente
- Accrual & working capital:
- One-off ricorrenti:

### 2.2 Solidità finanziaria
- Leva complessiva:
- Copertura interessi:
- Scadenze debito:
- Rischio rifinanziamento:

### 2.3 Red flags
(checklist Graham / Meredith)

### 2.4 Return on Capital

\[
ROC =
\frac{EBIT(1-T)}{Capital\ Invested}
\]

Interpretazione:
- ROC > costo del capitale → creazione valore
- ROC < costo del capitale → distruzione valore

Uso:
- verifica qualità economica reale
- supporto a Business Quality Pressure

**Output:** `Capital Preservation Pressure` (bloccante)

---

## 3. Narrative → Numbers → Test (Damodaran)

### 3.1 Narrativa
- Perché esiste valore qui? (≤10 righe)

### 3.2 Driver economici
- Ricavi:
- Margini:
- Reinvestimento:
- Rischio:

### 3.3 Falsificabilità
- Cosa deve accadere perché la narrativa sia sbagliata?
- Kill-switch non legati al prezzo:

**Output:** `Narrative Consistency Pressure`

---

## 4. Valuation Engine — Architettura tensionale

Il Valuation Engine non produce un valore puntuale ma una **tensione tra modelli di valore**.

I modelli utilizzati rappresentano poli interpretativi diversi:

- **Damodaran DCF** → polo narrativo / driver-based
- **EPV (Greenwald)** → polo prudente / senza crescita
- **Reverse DCF** → polo implicito del mercato

Il sistema produce sempre:

\[
V_{range} = [V_{prudente}, V_{narrativo}]
\]

Questo range alimenta:

- `Valuation Pressure`
- `Expectation Pressure`
- `Incoherence Log (IC-1)`
- PATCH Ascorbica

### 4.1 DCF driver-based (Damodaran)

Valore dell’impresa:

\[
V_{firm} =
\sum_{t=1}^{n}
\frac{FCFF_t}{(1+WACC)^t}
+
\frac{TV}{(1+WACC)^n}
\]

dove:

\[
FCFF =
EBIT(1-T)
+
Depreciation
-
CapEx
-
\Delta WC
\]

Terminal value:

\[
TV =
\frac{FCFF_{n+1}}{WACC-g}
\]

**Assunzioni chiave (dichiarate):**
- Crescita (coerente con life cycle):
- Margini target:
- Reinvestimento:
- Rischio (WACC):
- Crescita terminal sostenibile:

**Output:** `V_damodaran`

---

### 4.2 EPV — Earnings Power Value (Greenwald)

Valutazione prudente basata su utili normalizzati, senza crescita esplicita.

\[
EPV =
\frac{EBIT(1-T)}{WACC}
\]

Opzionalmente, se più coerente col titolo, usare una versione prudente su FCF normalizzato:

\[
V_{prudente} =
\frac{FCF_{norm}}{r}
\]

**Output:** `V_prudente`

---

### 4.3 Reverse DCF — aspettative implicite del mercato

Il Reverse DCF non produce un valore, ma una **crescita implicita** o una condizione implicita che il prezzo attuale sta scontando.

Forma semplificata:

\[
g_{imp} \approx
\frac{Price \times WACC - FCF}{FCF}
\]

oppure, in versione più rigorosa, si risolve il tasso di crescita \(g\) che rende:

\[
Price \approx
\sum_{t=1}^{n}
\frac{FCFF_t(g)}{(1+WACC)^t}
+
\frac{TV(g)}{(1+WACC)^n}
\]

**Uso:**
- capire che narrativa sta prezzando il mercato
- confrontarla con la narrativa propria
- generare `Expectation Pressure`

**Output:** `g_implicito` + `Expectation Pressure`

---

### 4.4 MOS e Valuation Compression

Centro del range:

\[
V_{mid} =
\frac{V_{prudente} + V_{damodaran}}{2}
\]

Margin of Safety:

\[
MOS =
\frac{V_{mid} - Price}{V_{mid}}
\]

Valuation Compression:

\[
VC =
\frac{Price}{V_{mid}}
\]

**Interpretazione:**
- `MOS` misura la distanza tra prezzo e centro del range
- `VC` misura la compressione del prezzo verso il centro del range
- nessuna delle due formule genera da sola una decisione

---

### 4.5 Tensione di valore e IC-1

L’incoerenza canonica resta sempre attiva:

- polo prudente = `V_prudente`
- polo narrativo = `V_damodaran`

Tensione di valore base:

\[
TI_{val} =
\frac{|V_{prudente} - V_{damodaran}|}{V_{mid}}
\times
(1 - MOS)
\]

Tensione di valore base (v1.2 completa):
\[
TI_{tot}^{v1.2} = \sqrt{TI_{val}^2 + TI_{narr}^2 + TI_{ciclo}^2 + TI_{tec}^2}
\]
(vedi PATCH SOI-QUANT v1.2 per dettagli e componente TI_tec).

Questa tensione non va risolta: va resa visibile e compensata dal sistema.

**Output obbligatorio del Valuation Engine:**
- `V_prudente`
- `V_damodaran`
- `V_range`
- `V_mid`
- `MOS`
- `VC`
- `g_implicito`
- `TI_val`

---

### 4.6 Output DCF / Valuation (ascorbico)

- Range di valore: stretto / medio / ampio
- Sensibilità critiche (top 5):
  - crescita
  - margini
  - reinvestimento
  - WACC
  - terminal growth
- Scenari narrativi:
  - Bear
  - Base
  - Bull

**Output:** `Valuation Pressure` + `Expectation Pressure` + `IC-1 attiva`

---

## 5. Sanity Check (Graham + Greenwald)

- Valore prudente esiste? sì/no
- EPV / FCF normalizzato coerente? sì/no
- Divergenze spiegabili? come?
- Il mercato sta prezzando una crescita incompatibile con la storia del business? sì/no

### Cash Flow Sanity

FCF Yield:

\[
FCF\ Yield =
\frac{FCF}{Market\ Cap}
\]

Interpretazione:
- Alto → possibile sottovalutazione o rischio
- Basso → aspettative elevate

Uso:
- confronto con altri titoli
- coerenza con narrativa

**Output:** `Reality Check Pressure`

---

## 6. Rischio & Cicli (Marks)

### 6.1 Rischi irreversibili
- Lista breve

### 6.2 Sensibilità al ciclo
- Early / Mid / Late / Downturn
- Effetti su utili, cassa, leva

### 6.3 Second-level thinking
- Cosa il mercato crede?
- Dove potrei sbagliare io?

**Output:** `Cycle & Risk Pressure` (bloccante/modulante)

---

## 7. Market Expectations (Damodaran)

- Aspettative implicite del mercato:
- Divergenze con la tua narrativa:
- Eventi che potrebbero riallinearle:


**Output:** `Expectation Pressure`

Il Reverse DCF (sez. 4.3) viene utilizzato per stimare
le aspettative implicite del mercato.

---

## 8. Analisi Tecnica — Contesto (Taylor)

> Tecnica = contesto, non segnale.

- Trend primario:
- Volatilità:
- Struttura del prezzo:
- Rischio eventi/gap:
- Liquidità:

**Output:** `Timing & Microstructure Pressure` (contestuale)

---

## 9. Pressure Map (PM)

Compilazione finale delle pressioni:
- Difesa capitale (bloccante)
- Qualità business (modulante)
- Valutazione (modulante)
- Aspettative (modulante)
- Ciclo & rischio (bloccante/modulante)
- Tecnica (contestuale)

---

## 10. Stability Window (SW)

- Stato: stabile / fragile / instabile
- Driver stabilità (≤3)
- Trigger instabilità (≤3)
- Kill-switch (2–5)

---

## 11. Allocation Move (AM) — candidato

- Cap massimo suggerito:
- Azione: incremento / riduzione / invariato
- Atto minimo consentito (AMC):
- Condizione di revisione:

---

## 12. Incoherence Log (IL)

### IC-1: valore prudente vs valore narrativo (con Tension Index v1.2)
- Come emerge qui:
- TI_val = ...
- TI_narr = ...
- TI_ciclo = ...
- TI_tec = ...
- TI_tot v1.2 = ...
- Compensazione adottata:

### Altre incoerenze
- Reverse DCF vs narrativa propria
- Micro vs macro
- Lungo periodo vs timing

---

## 13. Output STS

- PM pronta: sì/no
- SW pronta: sì/no
- AM candidato: sì/no
- Cosa manca per aumentare affidabilità:

---

**Fine documento.**
