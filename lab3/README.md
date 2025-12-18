# Information Security - Lab 3: Message Authentication & Integrity Attacks

Questo repository contiene il lavoro svolto per il terzo laboratorio del corso di **Information Security** presso l'**Università degli Studi di Padova** (A.A. 2024/2025). Il progetto esplora l'implementazione di schemi di autenticazione simmetrica e l'analisi della loro robustezza contro attacchi di sostituzione e contraffazione (forgery).

## 👥 Gruppo: CyberDucks
* **Andrea Andreozzi** 
* **Riccardo Scalco** 
* **Sergio Cibecchini** 
* **Luca Ferrari** 

## 🎯 Obiettivi del Laboratorio
L'obiettivo principale è stato lo sviluppo di un sistema di autenticazione dei messaggi basato su chiave simmetrica e la valutazione della sua sicurezza tramite simulazioni di attacchi informatici, analizzando come la dimensione del messaggio e della chiave influenzino la probabilità di successo dell'attaccante.

## 🛠️ Task e Implementazione

### 1. Implementazione dello Schema di Autenticazione (Task 1)
Sviluppo di un sistema per garantire l'integrità di un messaggio $u$ di lunghezza $M$ tramite un tag $t$ di lunghezza $K$:
* **Generazione Tag**: Implementazione della funzione `generate_tag(u, k)` che converte messaggio e chiave in base 10, ne calcola la somma delle cifre e produce un prodotto finale convertito poi in binario.
* **Firma e Verifica**: Funzioni `sign_message` per apporre il tag al messaggio e `verify_tag` per convalidare l'integrità del pacchetto ricevuto.

### 2. Attacco di Sostituzione (Task 2)
Simulazione di un attacco in cui un intercettatore (Eve) sostituisce un messaggio intercettato $(u, t)$ con un nuovo paio $(u', t')$ sperando che venga accettato dal destinatario:
* **Analisi della Probabilità**: Studio deterministico della probabilità di successo dell'attacco.
* **Valutazione Sperimentale**: Verifica della teoria tramite $10^5$ iterazioni, confermando che la probabilità di successo dipende inversamente dalla dimensione della chiave $K$.

### 3. Attacco di Contraffazione (Forgery Attack) (Task 3)
Implementazione di un attacco più complesso mirato a generare un tag valido per un messaggio scelto senza conoscere la chiave:
* **Valutazione Computazionale**: Analisi del tempo richiesto per l'attacco al crescere della dimensione del messaggio e della chiave.
* **Probabilità di Successo**: Dimostrazione che, a differenza dell'attacco di sostituzione, il forgery non ha una garanzia deterministica di successo al primo tentativo e la sua efficacia diminuisce drasticamente all'aumentare della lunghezza della chiave segreta.

## 💻 Tecnologie Utilizzate
* **Linguaggio**: Python
* **Librerie**:
  * `NumPy` per la gestione di array e operazioni matematiche.
  * `Matplotlib` per la visualizzazione delle correlazioni tra dimensione della chiave, tempi di calcolo e probabilità di successo.
  * `Time` per il benchmarking delle performance degli attacchi.
* **Ambiente**: Google Colab / Jupyter Notebook.

## 📂 Struttura dei File
* `code_CyberDucks3.ipynb`: Notebook contenente le funzioni di firma, verifica e gli script per simulare gli attacchi di sostituzione e forgery.
* `report_CyberDucks.pdf`: Relazione tecnica dettagliata con l'analisi dei risultati, grafici delle probabilità di successo e conclusioni sulla sicurezza dello schema implementato.
