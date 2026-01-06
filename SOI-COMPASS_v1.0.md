# SOI-COMPASS — Market & Time Orientation Layer
Versione: v1.0
Stato: attivo

Prerequisiti:
- SOI-KERNEL (immutabile)
- SOI-RL (input informativi validati con RIS)

---

## 0. Principio fondante
SOI-COMPASS non prevede il futuro.
Non genera segnali, non decide allocazioni, non modifica il valore intrinseco.

La Bussola serve a:
- orientare il sistema nel tempo
- descrivere il contesto di mercato
- valutare la fragilità del regime
- stimare la tolleranza all’errore temporale

Output: pressioni di contesto, non decisioni operative.

---

## 1. Architettura temporale (timing a regimi)
La Bussola opera su tre tempi strutturali, non su finestre fisse.

---

## 2. Tempo lungo — Regime
Orizzonte indicativo: 12–36 mesi  
Aggiornamento: raro

Domanda guida:
In quale regime strutturale si trova il sistema mercato?

Dimensioni osservate:
- credito: espansione / neutro / contrazione
- liquidità: abbondante / neutra / restrittiva
- inflazione: in accelerazione / stabile / in decelerazione
- politica monetaria: accomodante / neutra / restrittiva
- pendolo emotivo: euforia / equilibrio / paura

Output:
- regime dominante
- stabilità del regime: alta / media / bassa

---

## 3. Tempo medio — Transizione
Orizzonte indicativo: 3–9 mesi  
Aggiornamento: periodico

Domanda guida:
Il regime si sta rafforzando, indebolendo o invertendo?

Elementi qualitativi:
- cambiamento della narrativa macro
- divergenza tra aspettative e dati
- segnali iniziali di stress o sollievo
- aumento o riduzione dell’incertezza

Output:
- stato: entrata / uscita / permanenza nel regime
- intensità della transizione: debole / media / forte

---

## 4. Tempo breve — Attrito
Orizzonte indicativo: settimane – 2 mesi  
Aggiornamento: frequente

Domanda guida:
Quanto è fragile il mercato in questo momento?

Dimensioni osservate:
- volatilità: bassa / media / alta
- liquidità: fluida / tesa / critica
- rischio eventi (macro, geopolitici, utili): basso / medio / alto
- comportamento del prezzo: ordinato / nervoso / dislocato

Output:
- livello di attrito operativo
- reversibilità generale: alta / media / bassa

---

## 5. State Memory Log (SML)
La Bussola mantiene memoria dei regimi precedenti per evitare overfitting al presente.

Struttura SML:
- regime precedente
- periodo di validità
- eventi chiave osservati
- paure dominanti allora
- esiti reali osservati
- errori di valutazione riconosciuti

Scopo:
- distinguere veri turning point da falsi segnali
- riconoscere pattern ricorrenti di errore collettivo

---

## 6. Presente — Sintesi di contesto
Integrazione dei tre tempi.

Valutazioni finali:
- regime: stabile / in transizione / instabile
- sentiment dominante: euforia / neutro / paura
- fragilità sistemica: bassa / media / alta

Output:
- pressione di contesto attuale

---

## 7. Prossimo plausibile (non previsivo)
Orizzonte: mesi, non date.

Scenari descrittivi:
- scenario base plausibile
- scenario alternativo
- scenario di stress

Nessuna probabilità numerica.
Solo coerenza con il regime e con i dati osservabili.

---

## 8. Time-to-Error Window (TEW)
Quanto tempo è possibile restare sbagliati prima che il danno diventi serio?

Valutazione qualitativa:
- errore breve (settimane): reversibile / non reversibile
- errore medio (mesi): danno gestibile / strutturale
- errore lungo (anni): rottura di tesi / perdita permanente

Output:
- finestra di tolleranza all’errore temporale: breve / media / lunga

---

## 9. Web Research Integrity Protocol (WRIP)
Ogni informazione proveniente dal web deve essere valida oggi.

Requisiti obbligatori:
- data di acquisizione esplicita
- fonte primaria identificabile
- fonte secondaria se disponibile
- valutazione dell’affidabilità
- scadenza informativa stimata

---

## 10. Research Integrity Stamp (RIS)
Per ogni fonte web utilizzata:

- data di acquisizione
- fonte primaria
- fonte secondaria (se presente)
- tipo fonte: primaria / secondaria / opinione
- affidabilità stimata: alta / media / bassa
- rischio bias / agenda: basso / medio / alto
- scadenza informativa: breve / media / lunga

Regola:
- RIS incompleto → informazione esclusa
- fonti a bassa affidabilità entrano solo come rumore di mercato

---

## 11. Output finale Bussola
SOI-COMPASS fornisce a Kernel, EX e PM:

- stato del mercato: favorevole / neutro / ostile
- regime: stabile / transizione / instabile
- attrito operativo: basso / medio / alto
- Time-to-Error Window: breve / media / lunga

La Bussola non:
- modifica il valore intrinseco
- genera buy o sell
- suggerisce timing predittivo
- invalida le analisi fondamentali

---

## 12. Limiti dichiarati
SOI-COMPASS:
- non fa market timing
- non prevede movimenti
- non utilizza indicatori automatici
- non produce ottimismo o panico

Il suo unico scopo è:
orientare il sistema nel tempo mutevole senza distruggerne la coerenza.

Nota strutturale:
SOI-COMPASS è indipendente dal portafoglio.
Non utilizza dati di performance, esposizione o drawdown.
Varia esclusivamente in risposta a cambiamenti del contesto esterno
(validati tramite WRIP e RIS).


---

Fine documento.

