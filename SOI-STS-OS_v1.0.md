# SOI-STS-OS — Single Title System Operating Layer
Versione: v1.0
Stato: attivo
Dipendenze: SOI-KERNEL, SOI-RL, SOI-STS

---

## 1. Missione
Integrare SOI-RL e SOI-STS nel Kernel senza:
- introdurre logica duale
- produrre decisioni operative
- eliminare incoerenze

STS-OS è un orchestratore, non un decisore.

---

## 2. Componenti integrati

### 2.1 Input accettati
- Research Card (RL)
- PM candidata (STS)
- SW candidata (STS)
- AM candidato (STS)
- Incoherence Log (STS)

### 2.2 Output consentiti
- PM validata (per Kernel)
- SW validata (per Kernel)
- IL aggiornato
- Note di integrazione (meta)

---

## 3. Contratti di interfaccia

### 3.1 RL → STS-OS
RL può fornire:
- evidenze
- pressioni candidate
- trigger / kill-switch suggeriti

RL NON può:
- proporre allocazioni
- indicare timing operativo

---

### 3.2 STS → STS-OS
STS può fornire:
- PM candidata completa
- SW candidata completa
- AM candidato (non vincolante)
- Incoherence Log aggiornato

STS NON può:
- dichiarare stabilità finale
- chiudere incoerenze

---

## 4. Validazioni STS-OS (formali, non concettuali)

### 4.1 Completezza
- PM contiene almeno 1 pressione bloccante
- SW contiene almeno 1 kill-switch
- IL contiene almeno IC-1

Se NO → ritorno a STS (errore di forma)

---

### 4.2 Non-deriva logica
- Nessuna soglia numerica che “decide”
- Nessuna frase del tipo “se X allora Y”
- Nessun target di prezzo vincolante

Se rilevato → invalidare output

---

### 4.3 Tracciabilità
- Ogni pressione deve avere:
  - origine (RL / STS)
  - evidenza citata
- Ogni kill-switch deve essere non-prezzo

---

## 5. Incoerenza obbligatoria

### IC-1 (obbligatoria)
- Valore prudente (Graham)
- Valore stimato (Damodaran)

STS-OS verifica che:
- entrambe siano presenti
- nessuna delle due sia eliminata

Se IC-1 assente → sistema invalido

---

## 6. Passaggio al Kernel

STS-OS consegna al Kernel:
- PM validata
- SW validata
- IL aggiornato
- AM candidato come *input*, non decisione

Il Kernel:
- stabilizza le pressioni
- produce Allocation Move finale

---

## 7. Audit & Versioning
- Ogni integrazione genera:
  - timestamp
  - STS-ID
  - RL-ID utilizzati
- Nessuna modifica al Kernel consentita da STS-OS

---

## 8. Cosa STS-OS NON fa
- Non calcola DCF
- Non interpreta bilanci
- Non legge il prezzo
- Non decide buy/sell
- Non rassicura l’utente

---

Fine documento.
