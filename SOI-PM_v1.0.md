# SOI-PM — Portfolio Management & Risk Layer
Versione: v1.0
Stato: attivo

Prerequisiti:
- SOI-KERNEL (Allocation Move finale)
- SOI-COMPASS (regime, attrito, Time-to-Error Window)
- SOI-STS (analisi singolo titolo validata)
- SOI-EX (vincoli di esecuzione)
- SOI-RL (informazioni con RIS valido)

---

## 0. Principio fondante
SOI-PM non massimizza il rendimento.
SOI-PM gestisce:
- rischio aggregato
- sopravvivenza del portafoglio
- capacità di assorbire errori nel tempo

Il portafoglio è un sistema.
La perdita irreversibile è il vero nemico.

---

## 1. Ruolo del modulo
SOI-PM governa:
- quanto rischio totale è ammesso
- come il rischio è distribuito
- quanto errore è tollerabile simultaneamente

SOI-PM non decide:
- singoli titoli
- timing di entrata/uscita
- valutazioni fondamentali

---

## 2. Risk Budget Globale
Il rischio è una risorsa finita.

### 2.1 Dimensioni del Risk Budget
- rischio di mercato
- rischio settoriale
- rischio geografico / politico
- rischio valutario
- rischio di concentrazione
- rischio informativo (qualità dati)

Il Risk Budget varia in funzione della Bussola.

---

## 3. Regime-Based Risk Adjustment
Il Risk Budget viene modulato dal regime di mercato.

Indicazioni qualitative:
- regime stabile → rischio ammesso medio–alto
- regime in transizione → rischio ammesso medio
- regime instabile → rischio ammesso basso

SOI-PM non usa percentuali fisse.
Usa livelli relativi e prudenziali.

---

## 4. Concentration Control
La concentrazione amplifica l’errore.

Controlli obbligatori:
- singolo titolo
- singolo settore
- singola area geografica
- singolo fattore di rischio

Regola:
- alta convinzione non giustifica alta concentrazione
- concentrazione ammessa solo se errore reversibile

---

## 5. Correlation Drift Map (CDM)
Le correlazioni non sono stabili.

SOI-PM osserva:
- correlazioni in condizioni normali
- correlazioni in stress
- correlazioni in panic

Scopo:
- evitare falsa diversificazione
- ridurre esposizioni che collassano insieme

La CDM è qualitativa, non matematica.

---

## 6. Drawdown Tolerance
Il drawdown è informazione, non fallimento.

Valutazioni:
- drawdown atteso
- drawdown tollerabile
- drawdown strutturalmente pericoloso

Se il drawdown supera la tolleranza:
- riduzione del rischio
- nessuna “mediazione emotiva”

---

## 7. Time-to-Error Aggregato
SOI-PM integra il Time-to-Error Window dei singoli titoli.

Domanda guida:
Quanto tempo può il portafoglio restare sbagliato nel suo insieme?

Valutazioni:
- errore breve aggregato: assorbibile / non assorbibile
- errore medio aggregato: gestibile / strutturale
- errore lungo aggregato: rottura sistemica

---

## 8. Liquidità e Resilienza
La liquidità è una funzione di sicurezza, non di rendimento.

SOI-PM valuta:
- liquidità reale degli strumenti
- profondità di mercato in stress
- capacità di riduzione rapida

Regola:
- liquidità insufficiente → rischio ridotto a monte

---

## 9. Web Integrity & Information Risk
Il rischio informativo è rischio reale.

Controlli:
- presenza di news non verificate
- RIS incompleti o scaduti
- narrative dominanti non supportate dai dati

Azioni:
- riduzione temporanea del Risk Budget
- aumento dei margini di sicurezza

---

## 10. Portfolio Memory Log
Il portafoglio deve ricordare.

Struttura minima:
- regime di ingresso
- ipotesi dominanti
- errori riconosciuti
- cosa ha funzionato
- cosa ha fallito

Scopo:
- evitare ripetizione sistematica degli stessi errori
- riconoscere bias ricorrenti

---

## 11. Integrazione con SOI-EX
SOI-PM non esegue operazioni.

SOI-PM:
- fornisce limiti
- riduce o amplia il perimetro operativo
- impone rallentamenti se necessario

SOI-EX decide come agire all’interno dei limiti.

---

## 12. Output del modulo
SOI-PM produce:
- livello di rischio complessivo ammesso
- vincoli di concentrazione
- alert di correlazione
- indicazioni di riduzione o mantenimento del rischio

Nessuna azione diretta viene generata.

---

## 13. Limiti dichiarati
SOI-PM:
- non seleziona titoli
- non ottimizza il rendimento
- non prevede il mercato
- non elimina drawdown

Il suo unico scopo è:
mantenere il portafoglio vivo abbastanza a lungo da permettere al valore di emergere.

---

Fine documento.
