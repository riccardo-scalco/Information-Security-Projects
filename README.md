# Information Security - Laboratori di Crittografia e Sicurezza (A.A. 2024/2025)

Benvenuti nel repository dei **CyberDucks**. Questo spazio raccoglie l'intero lavoro progettuale e sperimentale svolto per il corso di **Information Security** presso l'**Università degli Studi di Padova**.

## 👥 Il Team: CyberDucks
Il gruppo è composto da:
* **Andrea Andreozzi** 
* **Riccardo Scalco** 
* **Sergio Cibecchini**
* **Luca Ferrari** 

## 📁 Struttura del Progetto
Il repository è organizzato in quattro moduli principali, ognuno dei quali affronta una sfida specifica della sicurezza delle informazioni, partendo dalla crittografia classica fino alla teoria della segretezza nei canali fisici.

### 🔐 Lab 1: Cifrari AES-like e Crittoanalisi
Analisi approfondita dei cifrari iterati a blocchi.
* **Implementazione**: Sviluppo di un cifrario semplificato con struttura S-T-L (Substitution, Transposition, Linear).
* **Attacchi**: Studio della linearità e implementazione di attacchi KPA (Known Plaintext Attack) e Meet-in-the-Middle per il recupero delle chiavi segrete.

### 📡 Lab 2: Comunicazione Sicura (Wiretap Channel)
Studio della segretezza dal punto di vista della teoria dell'informazione.
* **Codifica**: Implementazione del meccanismo di *Random Binning* e dei codici di Hamming per garantire affidabilità a Bob e incertezza ad Eve.
* **Analisi**: Valutazione della segretezza perfetta e analisi delle performance (BER vs SNR) in canali AWGN.

### ✍️ Lab 3: Integrità e Autenticazione
Sviluppo di meccanismi per la protezione dei messaggi contro manipolazioni.
* **Meccanismo**: Implementazione di uno schema di Message Authentication Code (MAC) simmetrico.
* **Simulazione**: Analisi della probabilità di successo di attacchi di sostituzione e di contraffazione (forgery) al variare della lunghezza della chiave e del messaggio.

### 🔑 Lab 4: Secret Key Agreement
Generazione di chiavi crittografiche tramite canali rumorosi e discussione pubblica.
* **Protocollo**: Sviluppo di un sistema per permettere ad Alice e Bob di concordare una chiave segreta sfruttando la correlazione tra segnali fisici.
* **Metriche**: Valutazione rigorosa di correttezza, uniformità statistica (entropia) e perdita di segretezza rispetto a un intercettatore.

## 🛠️ Tecnologie e Requisiti
Tutti i laboratori sono stati implementati in **Python** all'interno di ambienti **Jupyter Notebook / Google Colab**.

**Librerie principali utilizzate:**
* `NumPy`: Per la gestione di matrici, calcoli modulari e operazioni bitwise.
* `Matplotlib` & `Seaborn`: Per la visualizzazione dei dati, analisi BER e distribuzioni statistiche.
* `Scikit-learn`: Per l'analisi delle metriche di performance e calibrazione.
  
---
*Padova, Anno Accademico 2024/2025*
