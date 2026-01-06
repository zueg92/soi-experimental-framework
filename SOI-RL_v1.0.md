# PATCH — SOI-RL v1.1
## Estensione fonti: Email / Documenti / Web Market Research

### 0. Principio guida
RL è un *sistema di ingestione e normalizzazione*.
Non produce decisioni (BUY/SELL), produce **Evidenze** che generano **Pressioni candidate** e possibili impatti su SW.

---

## 1. Tipi di fonte supportati (Source Types)
Ogni Research Card (RC) deve dichiarare un Source Type:

- EMAIL_USER: email incollata dall’utente (testo o screenshot)
- EMAIL_TOOL: email lette via Gmail tool (solo lettura; nessuna azione su casella)
- DOC_USER: documenti caricati dall’utente (PDF, slide, epub, note)
- WEB_MKT: ricerca di mercato dal web (articoli, report, dataset, siti istituzionali)
- FILINGS: bilanci/relazioni/filings (quando disponibili)
- CALLS: earning call / transcript / presentazioni
- DATA: dataset/indicatori (macro, settore, prezzi, ecc.)

---

## 2. Normalizzazione (obbligatoria)
Qualunque fonte (email/doc/web) viene convertita in:
- Claim (affermazione)
- Evidence (dato/estratto che sostiene il claim)
- Uncertainty (cosa non sappiamo)
- Falsifier (cosa lo smentirebbe)

RL non accetta “opinioni nude”.

---

## 3. Griglia affidabilità (Reliability Grid)
Ogni RC usa 3 dimensioni (non numeriche):
- Provenienza: primaria / secondaria / terziaria
- Verificabilità: alta / media / bassa
- Incentivi/Conflitti: bassi / medi / alti

**Nota:** WEB_MKT tende a essere secondaria; preferire primaria quando possibile.

---

## 4. Citazioni e tracciabilità
### 4.1 Email
- EMAIL_USER: salvare i passaggi chiave in “Evidence grezza” (max 5 righe)
- EMAIL_TOOL: indicare mittente, data, oggetto + snippet rilevante (max 5 righe)

### 4.2 Documenti
- DOC_USER: citare pagina/slide e sezione (es. “p. 7”, “Slide 12”)

### 4.3 Web Market Research
- WEB_MKT: salvare:
  - titolo fonte
  - data (se presente)
  - tipo fonte (istituzionale, vendor, news, blog, forum)
  - breve estratto/parafrasi
  - cosa misurava davvero

---

## 5. Web Market Research (protocollo RL)
RL può usare il web per:
- dimensionamento mercato (TAM/SAM/SOM, se robusto)
- trend settoriali (adozione, prezzi, regolazione)
- competitor mapping
- struttura dei margini di settore
- rischi normativi

**Regola anti-deriva:**
- un dato web non diventa “verità”; diventa *pressione candidata* con affidabilità.

**Diversità fonti (minimo)**
Per claim importanti: almeno 2 fonti diverse
(es. istituzionale + report settore, o report + dataset).

---

## 6. Research Card (RC) — campi aggiornati
Aggiungere ai campi base:

- Source Type: (EMAIL_USER / DOC_USER / WEB_MKT / ecc.)
- Disclosure: (c’è conflitto di interessi nella fonte?)
- Trace: (pagina/slide oppure “email-date-subject” oppure “web-title-date”)
- Quote Policy: max 25 parole per fonte non-lyrical

---

## 7. Output RL verso STS e Kernel (immutato)
RL produce solo:
- Pressioni candidate (↑ ↓ ↔ + intensità)
- Impatti potenziali su SW (driver/trigger/kill-switch suggeriti)
- Tag conflitti (CONFLICT:[tema]) se due RC divergono

RL non produce:
- target di prezzo
- segnali buy/sell
- timing operativo

---

## 8. Privacy & sicurezza (pratico)
- Non inserire dati sensibili non necessari (IBAN, numeri documento, ecc.)
- Se un’email contiene dati personali, RL estrarrà solo ciò che serve all’evidenza.

---

Fine patch.
